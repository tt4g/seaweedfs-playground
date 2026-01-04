
FROM chrislusf/seaweedfs:4.04 AS seaweedfs-provider

FROM debian:trixie-20251229

RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt-get update

RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt-get update \
    && apt-get install -y --no-install-recommends \
        fuse3

# Copy `weed` command.
COPY --from=seaweedfs-provider \
    --chown=root:root \
    --chmod=755 \
    /usr/bin/weed /usr/bin/weed

# Customize `/etc/fuse.conf`.
RUN sed -e "s/#user_allow_other/user_allow_other/" -i /etc/fuse.conf

RUN mkdir -p /mnt/seaweedfs-playground
