FROM paritytech/ci-linux:production as builder
LABEL description="This is the build stage for Pirl. Here we create the binary."

ARG PROFILE=release
WORKDIR /pirl

COPY . /pirl

RUN cargo build --$PROFILE

# ===== SECOND STAGE ======

FROM debian:buster-slim
LABEL description="This is the 2nd stage: a very small image where we copy the Pirl binary."
ARG PROFILE=release
COPY --from=builder /pirl/target/$PROFILE/pirl /usr/local/bin

RUN useradd -m -u 1000 -U -s /bin/sh -d /pirl pirl && \
	mkdir -p /pirl/.local/share/pirl && \
	chown -R pirl:pirl /pirl/.local && \
	ln -s /pirl/.local/share/pirl /data && \
	rm -rf /usr/bin /usr/sbin

USER pirl
EXPOSE 30333 9933 9944
VOLUME ["/data"]

CMD ["/usr/local/bin/pirl"]
