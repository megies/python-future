all: build-deb-unsigned

build-deb-unsigned:
	debuild -i -us -uc -b

build-deb-signed:
	debuild --no-tgz-check
