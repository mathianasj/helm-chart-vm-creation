FROM quay.io/fedora/fedora AS builder

RUN dnf install -y qemu

COPY input.vdi .

RUN qemu-img convert -f vdi -O qcow2 input.vdi output.qcow2

FROM scratch

COPY --from=builder output.qcow2 /disk/