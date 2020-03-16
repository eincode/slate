---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - json

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - user
  - group

search: true
---

# Introduction

Floo backend is authenticated only with user id which is put in the `userid` header on each request, without it, server will return code `401 Unauthorized` and will not process your request.

### Base URL

https://iacr9wz5kh.execute-api.ap-northeast-1.amazonaws.com/staging
