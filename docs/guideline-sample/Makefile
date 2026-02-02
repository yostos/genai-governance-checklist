# ガイドラインサンプル ビルド用 Makefile

SRC = guideline-sample.md
OUT_HTML = guideline-sample.html

# pandoc オプション
PANDOC_OPTS = --standalone \
              --toc \
              --toc-depth=2 \
              --metadata title="生成AI利用ガイドライン" \
              --metadata lang=ja

.PHONY: all html clean

all: html

html: $(OUT_HTML)

$(OUT_HTML): $(SRC)
	pandoc $(PANDOC_OPTS) -o $@ $<

clean:
	rm -f $(OUT_HTML)
