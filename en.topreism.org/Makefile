.POSIX:
.PHONY: all push test
.SUFFIXES: .md .html

TMPL = wiki.tmpl
PAGES != find wiki -name '*.md' | sed 's/\.md/.html/g'

.md.html: $(TMPL)
	bf $< < $(TMPL) > $@

all: $(PAGES)
push: all
	git add .
	git commit $(CF)
	git push $(PF)
test: all
	# i know...
	python3 -m http.server 1337
