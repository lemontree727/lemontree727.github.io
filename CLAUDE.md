# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 개요

안수빈의 개인 홈페이지("안수빈의 아침")입니다. 빌드 도구, 패키지, 테스트가 없는 정적 사이트이며 `index.html` 한 파일에 HTML, CSS(`<style>`), JS(`<script>`)가 모두 들어 있습니다.

## 배포

- 저장소: https://github.com/lemontree727/lemontree727.github.io (브랜치 `main`)
- GitHub Pages로 https://lemontree727.github.io 에 배포되며, `main`에 push하면 1~2분 뒤 반영됩니다.
- 이 저장소의 git 작성자는 로컬 설정으로 `lemontree727 <lemontree727@users.noreply.github.com>`입니다. 전역 설정(`subinan-git`)은 다른 프로젝트용이므로 바꾸지 마세요.
- 로컬 확인은 `index.html`을 브라우저로 직접 열면 됩니다.

## 구조와 규칙

- `index.html`은 Claude Artifact 페이지 형식으로 작성되어 `<!doctype html>`, `<html>`, `<head>`, `<body>` 태그 없이 `<title>`부터 시작합니다. GitHub Pages에서는 이 골격이 자동으로 붙지 않으므로, 문서 구조를 고칠 때는 골격 추가 여부를 고려하세요.
- 색상은 `:root`의 CSS 변수(강변 아침 테마: `--river`, `--bloom` 등)로만 정의합니다. 다크 모드는 `@media (prefers-color-scheme: dark)` 안의 `:root:not([data-theme="light"])`와 `:root[data-theme="dark"]` 두 곳에 같은 값으로 정의되어 있으니, 색을 바꿀 때는 두 곳을 함께 수정하세요.
- 글꼴은 Google Fonts(Hahmlet, IBM Plex Sans KR, IBM Plex Mono)를 `--display`/`--body`/`--mono` 변수로 씁니다.
- 반응형 기준점은 `52rem`(2열 → 1열)과 `36rem`(내비게이션 숨김, 카드 세로 배치)입니다.
- 하단 스크립트가 "다음 수업" 날짜(매주 일요일 07:00 기준)와 푸터 연도를 계산해 `#next-class`, `#year`에 넣습니다. 수업 요일이나 시간을 바꾸면 이 스크립트도 함께 고쳐야 합니다.
- 본문은 한국어이며 `word-break: keep-all`을 씁니다.
