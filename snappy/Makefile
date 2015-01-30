all: clean
	cp -a ../usr/bin/uhome ./bin
	cp -a ../usr/bin/nest-update ./bin
	cp -a ../usr/bin/nest-away ./bin
	cp -a ../usr/bin/nest-away ./bin/nest-home
	cp -a ../README ./meta/readme.md
	cp -a ../usr/share/uhome/uhome.svg ./meta
	VER=`grep -m1 "^static char\s\+VersionM" ./BUILD/main.c | sed -e "s/\";//" -e "s/.*\"//"`; sed -i -e "s/^version:.*/version: $$VER/" ./meta/package.yaml
	VER=`head -n 1 ../debian/changelog | sed 's/^.*(//' | sed 's/).*//' | sed 's/-.*//'`; sed -i -e "s/^version:.*/version: $$VER/" ./meta/package.yaml
	snappy build .

clean:
	rm -rf *.snap bin/*
