#!/bin/sh

TEX_BIN=/cygdrive/C/texmf/miktex/bin
PDFLATEX=$TEX_BIN/pdflatex.exe

extract_page()
{
    OUTPUT_NAME=$1
    FIRST_PAGE=$2
    LAST_PAGE=$3

    gs -dFirstPage=$FIRST_PAGE \
       -dLastPage=$LAST_PAGE \
       -sDEVICE=pdfwrite \
       -sOutputFile=$OUTPUT_NAME \
       -dBATCH \
       -dNOPAUSE \
       bigode.pdf
}

CHAPTER_NAMES=("front_cover" "contents" "preface" "chapter0" "chapter1" "chapter2" "chapter3" "chapter4" "chapter5" "chapter6" "chapter7" "chapter8" "chapter9" "back_cover")

PAGES=(1 3 5 7 13 27 47 65 79 91 103 119 127 134 135)

ZIP_FILE=bigode.zip

rm $ZIP_FILE

$PDFLATEX bigode.tex
$PDFLATEX bigode.tex

zip -g $ZIP_FILE bigode.pdf

for (( i = 0; i < ${#CHAPTER_NAMES[@]}; i++ ))
do
    CHAPTER_NAME=${CHAPTER_NAMES[i]}
    CHAPTER_NUM=`echo $i | awk '{printf("%02d",$0);}'`
    OUTPUT_NAME=${CHAPTER_NUM}_${CHAPTER_NAME}.pdf
    extract_page $OUTPUT_NAME ${PAGES[i]} `expr ${PAGES[i+1]} - 1`
    
    zip -g $ZIP_FILE $OUTPUT_NAME
done
