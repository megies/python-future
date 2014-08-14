all: build-deb-unsigned

changelog:
	sed "1s/~XXX/~`lsb_release -cs`/" changelog.template > changelog

build-deb-unsigned: changelog
	debuild -i -us -uc -b
	mv ../../python-future_*.deb ../../python-future_*.build ../../python-future_*.changes ../../python3-future_*.deb .

build-deb-signed: changelog
	debuild --no-tgz-check
	mv ../../python-future_*.deb ../../python-future_*.build ../../python-future_*.changes ../../python3-future_*.deb .
