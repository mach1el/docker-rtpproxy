# RTPproxy on docker
![license](https://img.shields.io/github/license/mach1el/docker-rtpproxy?color=pink&style=plastic)
![Size](https://img.shields.io/github/repo-size/mach1el/docker-rtpproxy?style=plastic)
![imgsize](https://img.shields.io/docker/image-size/mich43l/rtpproxy?color=grey&style=plastic)

RTPproxy server for streaming RTP on SIP proxy/server such as: [Opensips](https://www.opensips.org/),[Kamailio](https://www.kamailio.org/w/)...

### Pull from hub
	docker pull mich43l/rtpproxy

### Build from source
	git clone https://github.com/mach1el/docker-rtpproxy.git && cd docker-rtpproxy
	docker image build -t docker-rtpproxy .
	
### Run
*	docker run -tid --rm --name=rtpproxy --network=host docker-rtpproxy
* docker run -tid --rm --name=rtpproxy --network=host -v /var/lib/rtpproxy-recording:/var/lib/rtpproxy-recording -v /var/spool/rtpproxy:/var/spool/rtpproxy
