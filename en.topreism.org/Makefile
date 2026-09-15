.POSIX:
.PHONY: all push test
.SUFFIXES: .md .html

TMPL = main.tmpl
PAGES != find wk -name '*.md' | sed 's/\.md/.html/g'

.md.html: $(TMPL)
	bf $< < $(TMPL) > $@

all: $(PAGES)
push: all
	git add .
	git commit $(CF)
	git push $(PF)
test: all 
	python3 -m http.server 1337
