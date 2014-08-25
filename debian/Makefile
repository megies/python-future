.PHONY: changelog clean

build-2: clean build-deb-unsigned-2

build-6: clean build-deb-unsigned-6

clean:
	rm -rf changelog control rules python-future.install

prepare-2:
	cp control.2 control
	cp rules.2 rules
	rm python-future.install -rf

prepare-6:
	cp control.6 control
	cp rules.6 rules
	cp python-future.install.6 python-future.install

changelog:
	sed "1s/~XXX/~`lsb_release -cs`/" changelog.template > changelog

build-deb-unsigned-2: changelog prepare-2
	debuild -i -us -uc -b
	mv ../../python-future_*.deb ../../python-future_*.build ../../python-future_*.changes .

build-deb-unsigned-6: changelog prepare-6
	debuild -i -us -uc -b
	mv ../../python-future_*.deb ../../python-future_*.build ../../python-future_*.changes ../../python3-future_*.deb .

#build-deb-signed-2: changelog prepare-2
#	debuild --no-tgz-check
#	mv ../../python-future_*.deb ../../python-future_*.build ../../python-future_*.changes .
#
#build-deb-signed-6: changelog prepare-6
#	debuild --no-tgz-check
#	mv ../../python-future_*.deb ../../python-future_*.build ../../python-future_*.changes ../../python3-future_*.deb .
