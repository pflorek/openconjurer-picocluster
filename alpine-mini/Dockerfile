# https://hub.docker.com/r/hypriot/rpi-alpine-scratch/

FROM hypriot/rpi-alpine-scratch

RUN apk update && \
	apk upgrade && \
	apk add bash && \
	rm -rf /var/cache/apk/*

CMD ["/bin/bash"]
