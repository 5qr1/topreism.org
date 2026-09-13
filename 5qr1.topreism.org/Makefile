.POSIX:
.PHONY: all push
.SUFFIXES: .md .html

TMPL = index.tmpl
BLOGS != find blog -name '*.md' | sed 's/\.md/.html/g'

.md.html: $(TMPL)
	bf $< < $(TMPL) > $@

all: index.html $(BLOGS)
push: all
	git add .
	git commit $(CF)
	git push $(PF)
