
all: \
	download \
	glapi.py glxapi.py wglapi.py \
	glsize.hpp

download: \
	enum.spec \
	enumext.spec \
	gl.spec \
	gl.tm \
	glxenum.spec \
	glxenumext.spec \
	glx.spec \
	glxext.spec \
	glx.tm \
	wglenum.spec \
	wglenumext.spec \
	wgl.spec \
	wglext.spec \
	wgl.tm

%.spec %.tm:
	wget -N http://www.opengl.org/registry/api/$@

glapi.py: glspec.py gl.tm gl.spec
	python glspec.py gl gl.tm gl.spec > $@

glxapi.py: glspec.py glx.tm glx.spec glxext.spec
	python glspec.py glX glx.tm glx.spec glxext.spec > $@

wglapi.py: glspec.py wgl.tm wgl.spec wglext.spec
	python glspec.py wgl wgl.tm wgl.spec wglext.spec > $@

glsize.hpp: glsize.py
	python glsize.py > $@

.PRECIOUS: %.spec %.tm