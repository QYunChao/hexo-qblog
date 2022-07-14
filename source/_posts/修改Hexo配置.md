---
title: 修改Hexo配置
date: 2022-07-14 23:12:08
tags:
  -	博客
---

修改Hexo配置并为线上部署做准备

<!--more-->

<!DOCTYPE html><html><head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <style>
            @charset "utf-8";
            *,
            *::after,
            *::before {
                margin: 0;
                padding: 0;
                box-sizing: border-box;
            }
            body {
                -webkit-font-smoothing: antialiased;
                -moz-osx-font-smoothing: grayscale;
                font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Segoe UI", "Helvetica Neue", "PingFang SC", "Noto Sans", "Noto Sans CJK SC", "Microsoft YaHei", "\5FAE\8F6F\96C5\9ED1", sans-serif;
                font-size: 16px;
                line-height: 24px;
                color: #222;
            }
            ::selection {
                background-color: rgba(107, 112, 184, 0.16);
            }
            #title {
                font-size: 36px;
                line-height: 54px;
                font-weight: 500;
            }
            h1 {
                margin: 28px 0 0;
                font-size: 28px;
                line-height: 42px;
            }
            h2 {
                margin: 24px 0 0;
                font-size: 24px;
                line-height: 26px;
            }
            h3 {
                margin: 20px 0 0;
                font-size: 20px;
                line-height: 30px;
            }
            p {
                margin: 16px 0 0;
                line-height: 24px;
            }
            blockquote {
                margin: 16px 0 0;
                padding: 0 0 0 20px;
                line-height: 24px;
                box-shadow: inset 4px 0 0 0 #EEEEEE;
            }
            ol,
            ul {
                padding: 8px 0 0 32px;
            }
            li {
                margin: 8px 0 0;
                line-height: 24px;
            }
            hr {
                margin: 16px 0 0;
                height: 1px;
                background-color: #e9e9e9;
                border: none;
            }
            img {
                width: 100%;
                display: block;
            }
            pre {
                margin: 12px 0 0;
                border-radius: 4px;
                padding: 12px;
                background-color: #f5f5f5;
                font-size: 14px;
                white-space: pre-wrap;
            }
            code {
                color: #657B83;
                font-size: inherit;
                border-radius: 4px;
                display: block;
            }
            p code,
            table code {
                display: inline;
                padding: 4px;
                background-color: #f5f5f5;
            }
            a,
            a u {
                color: rgb(61, 168, 245);
                font-size: 16px;
                line-height: 20px;
                text-decoration: none;
                cursor: pointer;
            }
            a:hover {
                text-decoration: underline;
            }
            table {
                margin: 32px 0 0;
                border-left: 1px solid #D8D8D8;
                border-top: 1px solid #D8D8D8;
                border-collapse: collapse;
                border-spacing: 0;
            }
            table td {
                table-layout: fixed;
                padding: 8px 12px;
                min-width: 200px;
                max-width: 1000px;
                border-right: 1px solid #D8D8D8;
                border-bottom: 1px solid #D8D8D8;
            }
            table a,
            table blockquote,
            table code,
            table h1,
            table h2,
            table h3,
            table li,
            table p {
                margin: 0;
            }
            table ol,
            table ul {
                padding: 0 0 0 30px;
            }
            footer {
                padding: 48px;
                background-color: #f5f5f5;
                display: flex;
                justify-content: center;
            }
            footer a {
                padding-left: 28px;
                line-height: 24px;
                height: 24px;
                color: #808080;
                background-image: url("https://dn-clients.teambition.net/thoughts/thoughts_logo.svg");
                background-size: 24px 24px;
                background-repeat: no-repeat;
            }
            #page {
                max-width: 1024px;
                min-height: calc(100vh - 120px);
                margin: 0 auto;
                padding: 72px;
            }
            /* 检查项 */
            [data-type="checkbox"] {
                padding-left: 15px;
            }
            [data-check="true"],
            [data-check="false"] {
                list-style-type: none;
                padding-left: 0;
            }
            [data-check="true"]::before,
            [data-check="false"]::before {
                content: "";
                width: 14px;
                height: 14px;
                border-radius: 4px;
                vertical-align: bottom;
                display: inline-block;
                margin: 5px 11px;
                background-position: 50%;
                background-repeat: no-repeat;
                box-shadow: inset 0 0 0 1px#ddd;
            }
            [data-check="true"]::before {
                background-color: #6B70B8;
                box-shadow: inset 0 0 0 1px #6B70B8;
                background-image: url("data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHN2ZyB3aWR0aD0iMTJweCIgaGVpZ2h0PSIxMnB4IiB2aWV3Qm94PSIwIDAgMTIgMTIiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8IS0tIEdlbmVyYXRvcjogU2tldGNoIDU0ICg3NjQ4MCkgLSBodHRwczovL3NrZXRjaGFwcC5jb20gLS0+CiAgICA8dGl0bGU+55S75p2/PC90aXRsZT4KICAgIDxkZXNjPkNyZWF0ZWQgd2l0aCBTa2V0Y2guPC9kZXNjPgogICAgPGcgaWQ9IueUu+advyIgc3Ryb2tlPSJub25lIiBzdHJva2Utd2lkdGg9IjEiIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CiAgICAgICAgPHBvbHlnb24gaWQ9InYiIGZpbGw9IiNGRkZGRkYiIGZpbGwtcnVsZT0ibm9uemVybyIgcG9pbnRzPSIyLjM0NzM1NTA3IDUuOTc5NTQ0MzcgMS42NDkzMzI2MyA2LjY5NTYyMDI1IDQuNTM2MjIwMiA5LjUwOTcyNDczIDEwLjM1MzA5MTMgMy43MDgwMjk4IDkuNjQ2OTA4NzIgMyA0LjUyODE3MzMzIDguMTA1MzgwNjgiPjwvcG9seWdvbj4KICAgIDwvZz4KPC9zdmc+");
            }
            /* 块样式 */
            [data-type="attachment"] a,
            [data-type="relation"] a,
            [data-type="embed"] a {
                font-size: 14px;
                line-height: 24px;
                height: 48px;
                overflow: hidden;
                text-overflow: ellipsis;
                white-space: nowrap;
                width: 100%;
                margin: 16px 0 0;
                display: block;
                padding: 12px 12px 12px 40px;
                color: #222!important;
                border-radius: 4px;
                transition: 0.3s ease;
                box-shadow: inset 0 0 0 1px #eeeeee;
                background-repeat: no-repeat;
                background-position: 12px 50%;
            }
            [data-type="attachment"] a:hover,
            [data-type="relation"] a:hover,
            [data-type="embed"] a:hover {
                text-decoration: none!important;
                background-color: #f5f5f5;
            }
            /* 行内样式 */
            [data-type="document"],
            [data-type="file"],
            [data-type="folder"],
            [data-type="teambition-task"],
            [data-type="teambition-file"],
            [data-type="teambition-folder"],
            [data-type="teambition-date"],
            [data-type="DATE"] {
                background-position: 4px 50%;
                padding: 0 4px 0 26px;
                background-repeat: no-repeat;
            }
            /* 类型图标 */
            [data-type="embed"] a {
                background-image: url("data:image/svg+xml;base64,PHN2ZwogICAgd2lkdGg9IjIwcHgiCiAgICBoZWlnaHQ9IjIwcHgiCiAgICB2aWV3Qm94PSIwIDAgMjAgMjAiCiAgICB2ZXJzaW9uPSIxLjEiCiAgICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciCiAgICB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8cGF0aAogICAgICAgIGQ9Ik0xMC4wMDAxLDE0LjU2ODQgQzEwLjA4MTEsMTQuNTY4NCAxMC4xNjExLDE0LjU4NDQgMTAuMjM2MSwxNC42MTY0IEwxNC42MDkxLDE2LjQ5MDQgTDE0LjYwOTEsNC4wODg0IEMxNC42MDkxLDMuNTk4NCAxNC4yMTAxLDMuMjAwNCAxMy43MjExLDMuMjAwNCBMNi4yNzkxLDMuMjAwNCBDNS43OTAxLDMuMjAwNCA1LjM5MTEsMy41OTg0IDUuMzkxMSw0LjA4ODQgTDUuMzkxMSwxNi40OTA0IEw5Ljc2NDEsMTQuNjE2NCBDOS44MzkxLDE0LjU4NDQgOS45MTkxLDE0LjU2ODQgMTAuMDAwMSwxNC41Njg0IEwxMC4wMDAxLDE0LjU2ODQgWiBNMTUuMjA5MSwxOC4wMDA0IEMxNS4xMjkxLDE4LjAwMDQgMTUuMDQ4MSwxNy45ODQ0IDE0Ljk3MzEsMTcuOTUyNCBMMTAuMDAwMSwxNS44MjA0IEw1LjAyNzEsMTcuOTUyNCBDNC44NDIxLDE4LjAzMTQgNC42MjgxLDE4LjAxMjQgNC40NjExLDE3LjkwMTQgQzQuMjkyMSwxNy43OTA0IDQuMTkxMSwxNy42MDI0IDQuMTkxMSwxNy40MDA0IEw0LjE5MTEsNC4wODg0IEM0LjE5MTEsMi45Mzc0IDUuMTI4MSwyLjAwMDQgNi4yNzkxLDIuMDAwNCBMMTMuNzIxMSwyLjAwMDQgQzE0Ljg3MjEsMi4wMDA0IDE1LjgwOTEsMi45Mzc0IDE1LjgwOTEsNC4wODg0IEwxNS44MDkxLDE3LjQwMDQgQzE1LjgwOTEsMTcuNjAyNCAxNS43MDgxLDE3Ljc5MDQgMTUuNTM5MSwxNy45MDE0IEMxNS40NDAxLDE3Ljk2NjQgMTUuMzI1MSwxOC4wMDA0IDE1LjIwOTEsMTguMDAwNCBMMTUuMjA5MSwxOC4wMDA0IFoiCiAgICAgICAgaWQ9ImJvb2ttYXJrIgogICAgICAgIGZpbGw9IiNBNkE2QTYiPjwvcGF0aD4KPC9zdmc+");
            }
            [data-type="DATE"] {
                color: #808080;
                background-image: url("data:image/svg+xml;base64,PHN2ZwogICAgd2lkdGg9IjIwcHgiCiAgICBoZWlnaHQ9IjIwcHgiCiAgICB2aWV3Qm94PSIwIDAgMjAgMjAiCiAgICB2ZXJzaW9uPSIxLjEiCiAgICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciCiAgICB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8cGF0aAogICAgICAgIGQ9Ik0xNS4yOTQsMy40MTIgQzE2LjM5NCwzLjQxMiAxNy4yOTQsNC4zMTIgMTcuMjk0LDUuNDEyIEwxNy4yOTQsMTYgQzE3LjI5NCwxNy4xIDE2LjM5NCwxOCAxNS4yOTQsMTggTDQuNzA2LDE4IEMzLjYwNiwxOCAyLjcwNiwxNy4xIDIuNzA2LDE2IEwyLjcwNiw1LjQxMiBDMi43MDYsNC4zMTIgMy42MDYsMy40MTIgNC43MDYsMy40MTIgTDYuMTQ2LDMuNDEyIEw2LjE0NiwyLjYgQzYuMTQ2LDIuMjY5IDYuNDE1LDIgNi43NDYsMiBDNy4wNzgsMiA3LjM0NiwyLjI2OSA3LjM0NiwyLjYgTDcuMzQ2LDMuNDEyIEwxMi42NTQsMy40MTIgTDEyLjY1NCwyLjYgQzEyLjY1NCwyLjI2OSAxMi45MjIsMiAxMy4yNTQsMiBDMTMuNTg2LDIgMTMuODU0LDIuMjY5IDEzLjg1NCwyLjYgTDEzLjg1NCwzLjQxMiBMMTUuMjk0LDMuNDEyIFogTTE1LjI5NCwxNi44IEMxNS43MjgsMTYuOCAxNi4wOTQsMTYuNDM0IDE2LjA5NCwxNiBMMTYuMDk0LDguMjgyIEwzLjkwNiw4LjI4MiBMMy45MDYsMTYgQzMuOTA2LDE2LjQzNCA0LjI3MiwxNi44IDQuNzA2LDE2LjggTDE1LjI5NCwxNi44IFogTTQuNzA2LDQuNjEyIEM0LjI3Miw0LjYxMiAzLjkwNiw0Ljk3OCAzLjkwNiw1LjQxMiBMMy45MDYsNy4wODIgTDE2LjA5NCw3LjA4MiBMMTYuMDk0LDUuNDEyIEMxNi4wOTQsNC45NzggMTUuNzI4LDQuNjEyIDE1LjI5NCw0LjYxMiBMMTMuODU0LDQuNjEyIEwxMy44NTQsNS4wMzggQzEzLjg1NCw1LjM2OSAxMy41ODYsNS42MzggMTMuMjU0LDUuNjM4IEMxMi45MjIsNS42MzggMTIuNjU0LDUuMzY5IDEyLjY1NCw1LjAzOCBMMTIuNjU0LDQuNjEyIEw3LjM0Niw0LjYxMiBMNy4zNDYsNS4wMzggQzcuMzQ2LDUuMzY5IDcuMDc4LDUuNjM4IDYuNzQ2LDUuNjM4IEM2LjQxNSw1LjYzOCA2LjE0Niw1LjM2OSA2LjE0Niw1LjAzOCBMNi4xNDYsNC42MTIgTDQuNzA2LDQuNjEyIFoiCiAgICAgICAgZmlsbD0iI0E2QTZBNiI+PC9wYXRoPgo8L3N2Zz4=");
            }
            [data-type="attachment"] a {
                background-image: url("data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHN2ZyB3aWR0aD0iMjBweCIgaGVpZ2h0PSIyMHB4IiB2aWV3Qm94PSIwIDAgMjAgMjAiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8IS0tIEdlbmVyYXRvcjogU2tldGNoIDU0ICg3NjQ4MCkgLSBodHRwczovL3NrZXRjaGFwcC5jb20gLS0+CiAgICA8dGl0bGU+ZnVqaWFuPC90aXRsZT4KICAgIDxkZXNjPkNyZWF0ZWQgd2l0aCBTa2V0Y2guPC9kZXNjPgogICAgPGRlZnM+CiAgICAgICAgPHBhdGggZD0iTTE0LDQgTDcuNiw0IEM0LjUxMiw0IDIsNi41MTIgMiw5LjYgQzIsMTIuNjg4IDQuNTEyLDE1LjIgNy42LDE1LjIgTDEyLjk5NiwxNS4yIEMxMy4zMjcsMTUuMiAxMy41OTYsMTQuOTMxIDEzLjU5NiwxNC42IEMxMy41OTYsMTQuMjY5IDEzLjMyNywxNCAxMi45OTYsMTQgTDcuNiwxNCBDNS4xNzQsMTQgMy4yLDEyLjAyNiAzLjIsOS42IEMzLjIsNy4xNzQgNS4xNzQsNS4yIDcuNiw1LjIgTDE0LDUuMiBDMTUuNTQ0LDUuMiAxNi44LDYuNDU2IDE2LjgsOCBDMTYuOCw5LjU0NCAxNS41NDQsMTAuOCAxNCwxMC44IEw3LjgxMywxMC44IEM3LjE1MiwxMC44IDYuNjE0LDEwLjI2MiA2LjYxNCw5LjYgQzYuNjE0LDguOTM4IDcuMTUyLDguNCA3LjgxMyw4LjQgTDEyLjk5Niw4LjQgQzEzLjMyNyw4LjQgMTMuNTk2LDguMTMyIDEzLjU5Niw3LjggQzEzLjU5Niw3LjQ2OSAxMy4zMjcsNy4yIDEyLjk5Niw3LjIgTDcuODEzLDcuMiBDNi40OSw3LjIgNS40MTQsOC4yNzcgNS40MTQsOS42IEM1LjQxNCwxMC45MjMgNi40OSwxMiA3LjgxMywxMiBMMTQsMTIgQzE2LjIwNiwxMiAxOCwxMC4yMDYgMTgsOCBDMTgsNS43OTQgMTYuMjA2LDQgMTQsNCBMMTQsNCBaIiBpZD0icGF0aC0xIj48L3BhdGg+CiAgICA8L2RlZnM+CiAgICA8ZyBpZD0iZnVqaWFuIiBzdHJva2U9Im5vbmUiIHN0cm9rZS13aWR0aD0iMSIgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj4KICAgICAgICA8bWFzayBpZD0ibWFzay0yIiBmaWxsPSJ3aGl0ZSI+CiAgICAgICAgICAgIDx1c2UgeGxpbms6aHJlZj0iI3BhdGgtMSI+PC91c2U+CiAgICAgICAgPC9tYXNrPgogICAgICAgIDx1c2UgaWQ9Imljb24tcGFwZXJjbGlwIiBmaWxsPSIjQTZBNkE2IiB4bGluazpocmVmPSIjcGF0aC0xIj48L3VzZT4KICAgIDwvZz4KPC9zdmc+");
            }
            [data-type="document"] {
                color: #808080;
                background-image: url("data:image/svg+xml;base64,PHN2ZwogICAgd2lkdGg9IjIwcHgiCiAgICBoZWlnaHQ9IjIwcHgiCiAgICB2aWV3Qm94PSIwIDAgMjAgMjAiCiAgICB2ZXJzaW9uPSIxLjEiCiAgICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciCiAgICB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8cGF0aAogICAgICAgIGQ9Ik0xMS4xMDA1MDUxLDIgTDE3LDcuODk5NDk0OTQgTDE3LDE2IEMxNywxNy4xMDQ1Njk1IDE2LjEwNDU2OTUsMTggMTUsMTggTDUsMTggQzMuODk1NDMwNSwxOCAzLDE3LjEwNDU2OTUgMywxNiBMMyw0IEMzLDIuODk1NDMwNSAzLjg5NTQzMDUsMiA1LDIgTDExLjEwMDUwNTEsMiBaIgogICAgICAgIGlkPSJQYXRoIgogICAgICAgIGZpbGwtb3BhY2l0eT0iMC4zIgogICAgICAgIGZpbGw9IiM2QjcwQjgiPjwvcGF0aD4KICAgIDxwYXRoCiAgICAgICAgZD0iTTE3LDggTDEzLDggQzExLjg5NTQzMDUsOCAxMSw3LjEwNDU2OTUgMTEsNiBMMTEsMiBMMTEuMTAwNTA1MSwyIEwxNyw3Ljg5OTQ5NDk0IEwxNyw4IFoiCiAgICAgICAgaWQ9IlBhdGgiCiAgICAgICAgZmlsbD0iIzZCNzBCOCI+PC9wYXRoPgogICAgPHJlY3QKICAgICAgICBpZD0iZG9jaWNvbi90aG91Z2h0LWRvYyIKICAgICAgICBmaWxsPSIjNkI3MEI4IgogICAgICAgIHg9IjUuNSIKICAgICAgICB5PSIxMSIKICAgICAgICB3aWR0aD0iOSIKICAgICAgICBoZWlnaHQ9IjEuNiIKICAgICAgICByeD0iMC44Ij48L3JlY3Q+CiAgICA8cmVjdAogICAgICAgIGlkPSJkb2NpY29uL3Rob3VnaHQtZG9jIgogICAgICAgIGZpbGw9IiM2QjcwQjgiCiAgICAgICAgeD0iNS41IgogICAgICAgIHk9IjE0IgogICAgICAgIHdpZHRoPSI0IgogICAgICAgIGhlaWdodD0iMS42IgogICAgICAgIHJ4PSIwLjgiPjwvcmVjdD4KPC9zdmc+");
            }
            [data-type="file"] {
                color: #808080;
                background-image: url("data:image/svg+xml;base64,PHN2ZwogICAgd2lkdGg9IjIwcHgiCiAgICBoZWlnaHQ9IjIwcHgiCiAgICB2aWV3Qm94PSIwIDAgMjAgMjAiCiAgICB2ZXJzaW9uPSIxLjEiCiAgICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciCiAgICB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8cGF0aAogICAgICAgIGQ9Ik0xMS4xMDA1MDUxLDIgTDE3LDcuODk5NDk0OTQgTDE3LDE2IEMxNywxNy4xMDQ1Njk1IDE2LjEwNDU2OTUsMTggMTUsMTggTDUsMTggQzMuODk1NDMwNSwxOCAzLDE3LjEwNDU2OTUgMywxNiBMMyw0IEMzLDIuODk1NDMwNSAzLjg5NTQzMDUsMiA1LDIgTDExLjEwMDUwNTEsMiBaIgogICAgICAgIGlkPSJQYXRoIgogICAgICAgIGZpbGwtb3BhY2l0eT0iMC4zIgogICAgICAgIGZpbGw9IiM2QjcwQjgiPjwvcGF0aD4KICAgIDxwYXRoCiAgICAgICAgZD0iTTE3LDggTDEzLDggQzExLjg5NTQzMDUsOCAxMSw3LjEwNDU2OTUgMTEsNiBMMTEsMiBMMTEuMTAwNTA1MSwyIEwxNyw3Ljg5OTQ5NDk0IEwxNyw4IFoiCiAgICAgICAgaWQ9IlBhdGgiCiAgICAgICAgZmlsbD0iIzZCNzBCOCI+PC9wYXRoPgo8L3N2Zz4=");
            }
            [data-type="folder"] {
                color: #808080;
                background-image: url("data:image/svg+xml;base64,PHN2ZwogICAgd2lkdGg9IjIwcHgiCiAgICBoZWlnaHQ9IjIwcHgiCiAgICB2aWV3Qm94PSIwIDAgMjAgMjAiCiAgICB2ZXJzaW9uPSIxLjEiCiAgICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciCiAgICB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8cGF0aAogICAgICAgIGQ9Ik0xNi41LDUgQzE3LjYwNDU2OTUsNSAxOC41LDUuODk1NDMwNSAxOC41LDcgTDE4LjUsOCBMMS41LDggQzEuNSw3LjM3MDczNTg5IDEuNSw2LjM3MDczNTg5IDEuNSw1IEMxLjUsMy44OTU0MzA1IDIuMzk1NDMwNSwzIDMuNSwzIEw3LjI3NjQ2OTQ1LDMgQzcuNTYyNDk1NDcsMyA3LjgzNDgzMDg0LDMuMTIyNDc4ODEgOC4wMjQ2MTgwMywzLjMzNjQ2ODc3IEw5LjUsNSBMMTYuNSw1IFoiCiAgICAgICAgaWQ9ImZvbGRlcmljb24vdGhvdWdodC1mb2xkZXIiCiAgICAgICAgZmlsbD0iIzZCNzBCOCI+PC9wYXRoPgogICAgPHBhdGgKICAgICAgICBkPSJNMS41LDggTDE4LjUsOCBMMTguNSwxNSBDMTguNSwxNi4xMDQ1Njk1IDE3LjYwNDU2OTUsMTcgMTYuNSwxNyBMMy41LDE3IEMyLjM5NTQzMDUsMTcgMS41LDE2LjEwNDU2OTUgMS41LDE1IEwxLjUsOCBaIgogICAgICAgIGlkPSJmb2xkZXJpY29uL3Rob3VnaHQtZm9sZGVyIgogICAgICAgIGZpbGwtb3BhY2l0eT0iMC4zIgogICAgICAgIGZpbGw9IiM2QjcwQjgiPjwvcGF0aD4KPC9zdmc+");
            }
            [data-type="teambition-task"] {
                color: #808080;
                background-image: url("data:image/svg+xml;base64,PHN2ZwogICAgd2lkdGg9IjIwcHgiCiAgICBoZWlnaHQ9IjIwcHgiCiAgICB2aWV3Qm94PSIwIDAgMjAgMjAiCiAgICB2ZXJzaW9uPSIxLjEiCiAgICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciCiAgICB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8cmVjdAogICAgICAgIGlkPSJ0YXNraWNvbi90Yi10YXNrIgogICAgICAgIGZpbGwtb3BhY2l0eT0iMC4zIgogICAgICAgIGZpbGw9IiMzREE4RjUiCiAgICAgICAgeD0iMyIKICAgICAgICB5PSIzIgogICAgICAgIHdpZHRoPSIxNCIKICAgICAgICBoZWlnaHQ9IjE0IgogICAgICAgIHJ4PSIyIj48L3JlY3Q+CiAgICA8cGF0aAogICAgICAgIGQ9Ik05Ljk0OTAyNzg5LDEwLjg3MDMzMTkgTDE3LjQzNjE4NTMsMy40MzI0NTAwNCBDMTcuNzQ5NjM0NSwzLjEyMTA2Mzc2IDE4LjI1NjE2MzcsMy4xMjI3MzYwOSAxOC41Njc1NSwzLjQzNjE4NTI4IEMxOC44Nzg5MzYyLDMuNzQ5NjM0NDcgMTguODc3MjYzOSw0LjI1NjE2MzY5IDE4LjU2MzgxNDcsNC41Njc1NDk5NiBMMTAuNTEwODE1MiwxMi41Njc1NSBDMTAuMTk4MDMzNywxMi44NzgyNzI5IDkuNjkyODE2MjcsMTIuODc3MzY2MiA5LjM4MTE1MjE1LDEyLjU2NTUyMjUgTDYuNDM0MTUxNzEsOS42MTY4MjQ0NyBDNi4xMjE4MjIyNSw5LjMwNDMxNTA5IDYuMTIxOTY4MSw4Ljc5Nzc4MzEzIDYuNDM0NDc3NDgsOC40ODU0NTM2NyBDNi43NDY5ODY4Niw4LjE3MzEyNDIxIDcuMjUzNTE4ODIsOC4xNzMyNzAwNiA3LjU2NTg0ODI5LDguNDg1Nzc5NDQgTDkuOTQ5MDI3ODksMTAuODcwMzMxOSBaIgogICAgICAgIGlkPSJQYXRoIgogICAgICAgIGZpbGw9IiMzREE4RjUiCiAgICAgICAgZmlsbC1ydWxlPSJub256ZXJvIj48L3BhdGg+Cjwvc3ZnPg==");
            }
            [data-type="teambition-file"] {
                color: #808080;
                background-image: url("data:image/svg+xml;base64,PHN2ZwogICAgd2lkdGg9IjIwcHgiCiAgICBoZWlnaHQ9IjIwcHgiCiAgICB2aWV3Qm94PSIwIDAgMjAgMjAiCiAgICB2ZXJzaW9uPSIxLjEiCiAgICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciCiAgICB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8cGF0aAogICAgICAgIGQ9Ik0xMS4xMDA1MDUxLDIgTDE3LDcuODk5NDk0OTQgTDE3LDE2IEMxNywxNy4xMDQ1Njk1IDE2LjEwNDU2OTUsMTggMTUsMTggTDUsMTggQzMuODk1NDMwNSwxOCAzLDE3LjEwNDU2OTUgMywxNiBMMyw0IEMzLDIuODk1NDMwNSAzLjg5NTQzMDUsMiA1LDIgTDExLjEwMDUwNTEsMiBaIgogICAgICAgIGlkPSJQYXRoIgogICAgICAgIGZpbGwtb3BhY2l0eT0iMC4zIgogICAgICAgIGZpbGw9IiMzREE4RjUiPjwvcGF0aD4KICAgIDxwYXRoCiAgICAgICAgZD0iTTE3LDggTDEzLDggQzExLjg5NTQzMDUsOCAxMSw3LjEwNDU2OTUgMTEsNiBMMTEsMiBMMTEuMTAwNTA1MSwyIEwxNyw3Ljg5OTQ5NDk0IEwxNyw4IFoiCiAgICAgICAgaWQ9IlBhdGgiCiAgICAgICAgZmlsbD0iIzNEQThGNSI+PC9wYXRoPgo8L3N2Zz4=");
            }
            [data-type="teambition-folder"] {
                color: #808080;
                background-image: url("data:image/svg+xml;base64,PHN2ZwogICAgd2lkdGg9IjIwcHgiCiAgICBoZWlnaHQ9IjIwcHgiCiAgICB2aWV3Qm94PSIwIDAgMjAgMjAiCiAgICB2ZXJzaW9uPSIxLjEiCiAgICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciCiAgICB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8cGF0aAogICAgICAgIGQ9Ik0xNi41LDUgQzE3LjYwNDU2OTUsNSAxOC41LDUuODk1NDMwNSAxOC41LDcgTDE4LjUsOCBMMS41LDggQzEuNSw3LjM3MDczNTg5IDEuNSw2LjM3MDczNTg5IDEuNSw1IEMxLjUsMy44OTU0MzA1IDIuMzk1NDMwNSwzIDMuNSwzIEw3LjI3NjQ2OTQ1LDMgQzcuNTYyNDk1NDcsMyA3LjgzNDgzMDg0LDMuMTIyNDc4ODEgOC4wMjQ2MTgwMywzLjMzNjQ2ODc3IEw5LjUsNSBMMTYuNSw1IFoiCiAgICAgICAgaWQ9ImZvbGRlcmljb24vdGItZm9sZGVyIgogICAgICAgIGZpbGw9IiMzREE4RjUiPjwvcGF0aD4KICAgIDxwYXRoCiAgICAgICAgZD0iTTEuNSw4IEwxOC41LDggTDE4LjUsMTUgQzE4LjUsMTYuMTA0NTY5NSAxNy42MDQ1Njk1LDE3IDE2LjUsMTcgTDMuNSwxNyBDMi4zOTU0MzA1LDE3IDEuNSwxNi4xMDQ1Njk1IDEuNSwxNSBMMS41LDggWiIKICAgICAgICBpZD0iZm9sZGVyaWNvbi90Yi1mb2xkZXIiCiAgICAgICAgZmlsbC1vcGFjaXR5PSIwLjMiCiAgICAgICAgZmlsbD0iIzNEQThGNSI+PC9wYXRoPgo8L3N2Zz4=");
            }
            [data-type="teambition-date"] {
                color: #808080;
                background-image: url("data:image/svg+xml;base64,PHN2ZwogICAgd2lkdGg9IjIwcHgiCiAgICBoZWlnaHQ9IjIwcHgiCiAgICB2aWV3Qm94PSIwIDAgMjAgMjAiCiAgICB2ZXJzaW9uPSIxLjEiCiAgICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciCiAgICB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+CiAgICA8cmVjdAogICAgICAgIGlkPSJkYXRlaWNvbi90Yi1kYXRlIgogICAgICAgIGZpbGwtb3BhY2l0eT0iMC4zIgogICAgICAgIGZpbGw9IiMzREE4RjUiCiAgICAgICAgeD0iMiIKICAgICAgICB5PSI0IgogICAgICAgIHdpZHRoPSIxNiIKICAgICAgICBoZWlnaHQ9IjEzIgogICAgICAgIHJ4PSIyIj48L3JlY3Q+CiAgICA8cGF0aAogICAgICAgIGQ9Ik00LDQgTDE2LDQgQzE3LjEwNDU2OTUsNCAxOCw0Ljg5NTQzMDUgMTgsNiBMMTgsOCBMMiw4IEwyLDYgQzIsNC44OTU0MzA1IDIuODk1NDMwNSw0IDQsNCBaIgogICAgICAgIGlkPSJkYXRlaWNvbi90Yi1kYXRlIgogICAgICAgIGZpbGw9IiMzREE4RjUiPjwvcGF0aD4KICAgIDxwYXRoCiAgICAgICAgZD0iTTYuNiwyIEw2LjYsMiBDNy4wNDE4Mjc4LDIgNy40LDIuMzU4MTcyMiA3LjQsMi44IEw3LjQsNiBMNS44LDYgTDUuOCwyLjggQzUuOCwyLjM1ODE3MjIgNi4xNTgxNzIyLDIgNi42LDIgWiIKICAgICAgICBpZD0iZGF0ZWljb24vdGItZGF0ZSIKICAgICAgICBmaWxsPSIjM0RBOEY1Ij48L3BhdGg+CiAgICA8cGF0aAogICAgICAgIGQ9Ik0xMy40LDIgTDEzLjQsMiBDMTMuODQxODI3OCwyIDE0LjIsMi4zNTgxNzIyIDE0LjIsMi44IEwxNC4yLDYgTDEyLjYsNiBMMTIuNiwyLjggQzEyLjYsMi4zNTgxNzIyIDEyLjk1ODE3MjIsMiAxMy40LDIgWiIKICAgICAgICBpZD0iZGF0ZWljb24vdGItZGF0ZSIKICAgICAgICBmaWxsPSIjM0RBOEY1Ij48L3BhdGg+Cjwvc3ZnPg==");
            }
        </style>
    <title>修改Hexo配置</title></head>
    <body>
        <div id="page"><div id="title">修改Hexo配置</div><p data-key="62ccf0f75a26fa0012d0755a" data-type="paragraph"><strong>标签：</strong><span style="color: #A6A6A6">Hexo、博客</span></p><p data-key="62ccf1dd5a26fa0012d0756d" data-type="paragraph"><strong>作者</strong>：<span style="color: #bfbfbf">邱昀晁</span></p><p data-key="62ccf0f75a26fa0012d0755b" data-type="paragraph"><strong>发布时间：</strong><span data-key="thoughts-779567" data-type="DATE">2022-07-12</span></p><p data-key="62ce899df0324900126698f5" data-type="paragraph"></p><p data-key="62ccf0f75a26fa0012d0755e" data-type="paragraph">上次我们说到，修改主题为 <span style="color: #e62412">tangyuxian</span>，该主题基于 <a data-key="thoughts-779568" data-type="LINK" href="https://github.com/tangyuxian/hexo-theme-nexmoe"><strong>hexo-theme-nexmoe</strong></a> 深度定制，使用前需要做一些基本配置，具体教程如下。</p><hr data-key="62ce8a8df0324900126698f6" data-type="hr"><h1 data-key="62ccf0f75a26fa0012d0755f" data-type="header-one">删除无用的配置文件</h1><p data-key="62cd7f9b31866300123e84aa" data-type="paragraph">修改配置之前，我们先删除一些无用的文件，如图：</p><img data-key="62cd81a331866300123e84b7" data-type="image" src="./62cd81a331866300123e84b7.png" alt="image.png"><p data-key="62ccf18d5a26fa0012d07569" data-type="paragraph">这个文件是默认主题 landscape 的配置文件，对我们来说已经没有意义，删除即可。</p><img data-key="62ceab7275d10e001253b51d" data-type="image" src="./62ceab7275d10e001253b51d.png" alt="image.png"><p data-key="62ce8c0ef03249001266993d" data-type="paragraph">由于我们在根目录中已经有了<span style="color: #e62412">_config.tangyuxian.yml</span>，所以<span style="color: #e62412">themes\tangyuxian</span>中的<span style="color: #e62412">_config.yml</span>也可以删除了。</p><p data-key="62ceac0875d10e001253b51f" data-type="paragraph"></p><h1 data-key="62ceab7c75d10e001253b51e" data-type="header-one">主题教程</h1><ol data-key="thoughts-779570" data-type="ordered-list-wrapper"><li data-key="thoughts-779524" data-type="ordered-list-item">使用本主题包前请阅读 <a data-key="thoughts-779569" data-type="LINK" href="https://hexo.io/zh-cn/docs/">HEXO官方文档</a>，本主题包仅适用于HEXO,请确认您已安装HEXO相关依赖</li><li data-key="thoughts-779525" data-type="ordered-list-item">开始使用本主题</li></ol><ul data-key="thoughts-779571" data-type="unordered-list-wrapper"><li data-key="thoughts-779526" data-type="unordered-list-item">注意安装<span style="color: #6e74e0"><code>wordcount</code></span>插件,用来激活字数统计功能:<span style="color: #6e74e0"><code>npm i --save hexo-wordcount</code></span></li><li data-key="thoughts-779527" data-type="unordered-list-item">请修改位于您项目根目录的<span style="color: #6e74e0"><code>_config.yml</code></span>的文件,将默认代码高亮关闭处理</li></ul><pre data-key="62ce8e66f0324900126699a5" data-type="code-wrapper"><code data-key="thoughts-779528" data-type="code-block">highlight:  </code><code data-key="thoughts-779529" data-type="code-block">	enable: false</code></pre><p data-key="62ce8ffbf0324900126699c8" data-type="paragraph">这点非常重要，不然在写文章的时候如果有代码会高亮异常，如下：</p><img data-key="62ce9028f0324900126699c9" data-type="image" style="text-align: center;" src="./62ce9028f0324900126699c9.png" alt="image.png"><p data-key="62ce905ff0324900126699ca" data-type="paragraph">配置正确则是这样的：</p><img data-key="62ce9073f0324900126699cc" data-type="image" style="text-align: center;" src="./62ce9073f0324900126699cc.png" alt="image.png"><ul data-key="thoughts-779572" data-type="unordered-list-wrapper"><li data-key="thoughts-779530" data-type="unordered-list-item">设置文章信息</li></ul><pre data-key="62ce8e2af0324900126699a1" data-type="code-wrapper"><code data-key="thoughts-779531" data-type="code-block">---</code><code data-key="thoughts-779532" data-type="code-block">title: 此处为标题</code><code data-key="thoughts-779533" data-type="code-block">date: 此处为时间</code><code data-key="thoughts-779534" data-type="code-block">tags:</code><code data-key="thoughts-779535" data-type="code-block">- 标签1</code><code data-key="thoughts-779536" data-type="code-block">- 标签2</code><code data-key="thoughts-779537" data-type="code-block">categories:</code><code data-key="thoughts-779538" data-type="code-block">- 分组名</code><code data-key="thoughts-779539" data-type="code-block">cover: /images/post/markerdown.jpg(可选:封面地址,可以是相对也可以是绝对路径)</code><code data-key="thoughts-779540" data-type="code-block">coverWidth: 1200(可选:封面宽度)</code><code data-key="thoughts-779541" data-type="code-block">coverHeight: 320(可选:封面高度)</code><code data-key="thoughts-779542" data-type="code-block">author:文章作者(可选)</code><code data-key="thoughts-779543" data-type="code-block">from:文章来源(可选)</code><code data-key="thoughts-779544" data-type="code-block">---</code></pre><ul data-key="thoughts-779573" data-type="unordered-list-wrapper"><li data-key="thoughts-779545" data-type="unordered-list-item">自动通过标签来匹配封面(beta)</li></ul><p data-key="62ce8ec0f0324900126699ac" data-type="paragraph">目前标签名对应的封面配置位置在主题根目录(<code>/source/js/postcover.js</code>),可在该文件下配置标签对应的封面,文章封面的优先级是(文章md文件配置的封面&gt;自动匹配的封面&gt;在主题包<code>_config.yml</code>全局设置的背景图)</p><ul data-key="thoughts-779574" data-type="unordered-list-wrapper"><li data-key="thoughts-779546" data-type="unordered-list-item">文章归档</li></ul><p data-key="62ce8ecff0324900126699ae" data-type="paragraph">为了让文章归档到一个页面,请在项目的根目录<code>/source/</code>下创建<code>archives.md</code>文件,文件内填写如下内容即可:</p><pre data-key="62ce8efcf0324900126699b1" data-type="code-wrapper"><code data-key="thoughts-779547" data-type="code-block">---</code><code data-key="thoughts-779548" data-type="code-block">title: 文章归档</code><code data-key="thoughts-779549" data-type="code-block">layout: archives</code><code data-key="thoughts-779550" data-type="code-block">permalink: archives.html</code><code data-key="thoughts-779551" data-type="code-block">---</code></pre><ul data-key="thoughts-779575" data-type="unordered-list-wrapper"><li data-key="thoughts-779552" data-type="unordered-list-item">更多...</li></ul><ol data-key="thoughts-779576" data-type="ordered-list-wrapper"><li data-key="thoughts-779553" data-type="ordered-list-item">将本主题下载后放至您的hexo项目根目录的 <code>themes</code> 下,并开启使用本主题</li><li data-key="thoughts-779554" data-type="ordered-list-item">以下是本主题包的目录结构图</li></ol><pre data-key="62ce8f2ef0324900126699b5" data-type="code-wrapper"><code data-key="thoughts-779555" data-type="code-block">├── languages       //国际化语言包</code><code data-key="thoughts-779556" data-type="code-block">├── layout			//ejs模板布局文件夹</code><code data-key="thoughts-779557" data-type="code-block">├── scripts         //自定义执行脚本		</code><code data-key="thoughts-779558" data-type="code-block">├── source          //静态资源文件夹</code><code data-key="thoughts-779559" data-type="code-block">├── _config.styl	//样式配置文件</code><code data-key="thoughts-779560" data-type="code-block">├── _config.yml		//主题配置文件</code><code data-key="thoughts-779561" data-type="code-block">├── package.json    //node配置项</code><code data-key="thoughts-779562" data-type="code-block">└── README.md       //说明文档</code></pre><p data-key="62ce8c3bf032490012669942" data-type="paragraph"><code>_config.yml</code>属于本主题核心配置项,本主题的所有功能性内容将在本主题中配置注:静态立绘板的配置图在 <code>background character</code> 中</p><ol data-key="thoughts-779577" data-type="ordered-list-wrapper"><li data-key="thoughts-779563" data-type="ordered-list-item">即时通讯插件</li></ol><p data-key="62ce8f5bf0324900126699b9" data-type="paragraph"><code>daovoice</code>需要您到<a data-key="thoughts-779578" data-type="LINK" href="http://dashboard.daovoice.io/">daovoice官网</a>申请key并配置</p><ol data-key="thoughts-779579" data-type="ordered-list-wrapper"><li data-key="thoughts-779564" data-type="ordered-list-item">主题色个性化配置</li></ol><p data-key="62ce8f6af0324900126699be" data-type="paragraph"><code>_config.styl</code>属于本主题个性化配置项,主题色和部分插件的自定义图案可在该配置项中配置,未来版本会不断扩展可配置内容</p><ol data-key="thoughts-779580" data-type="ordered-list-wrapper"><li data-key="thoughts-779565" data-type="ordered-list-item">本地搜索功能依赖</li></ol><p data-key="62ce8fb5f0324900126699c4" data-type="paragraph">参考<a data-key="thoughts-779581" data-type="LINK" href="https://www.npmjs.com/package/hexo-generator-search">hexo-generator-search</a>,配置相关参数,用于生成<code>search.xml</code>,本地搜索依赖该文件进行检索</p><ol data-key="thoughts-779582" data-type="ordered-list-wrapper"><li data-key="thoughts-779566" data-type="ordered-list-item">看板娘配置方法</li></ol><p data-key="62ce8fb5f0324900126699c6" data-type="paragraph">参考<a data-key="thoughts-779583" data-type="LINK" href="https://github.com/tangyuxian/hexo-helper-live2d">hexo-helper-live2d</a>配置看板娘插件.附赠更多丰富的看板娘插件<a data-key="thoughts-779584" data-type="LINK" href="https://github.com/tangyuxian/live2D">live2D大礼包</a>(ps:里面有超级萌小埋哦)</p><p data-key="62ce8c3bf032490012669944" data-type="paragraph"></p><h1 data-key="62cd81b231866300123e84b8" data-type="header-one">配置Git</h1><p data-key="62cd81b231866300123e84b9" data-type="paragraph">关于什么是Git，这里我不再赘述，在本项目中我选择的存储库是GitHub。</p><p data-key="62cd830631866300123e84be" data-type="paragraph"></p><h2 data-key="62cd830631866300123e84bf" data-type="header-two">配置.gitignore</h2><p data-key="62cd833331866300123e84c0" data-type="paragraph">在.gitignore文件中加上一些忽略文件，如.log等。</p><p data-key="62cd82e831866300123e84bb" data-type="paragraph"></p><h2 data-key="62cd839731866300123e84c1" data-type="header-two">完成初次代码提交</h2><p data-key="62cd83a631866300123e84c2" data-type="paragraph">初始化提交代码</p><p data-key="62cd83b531866300123e84c3" data-type="paragraph"></p><h1 data-key="62cd82e831866300123e84bc" data-type="header-one">个性化配置博客</h1><h2 data-key="62ceac6775d10e001253b522" data-type="header-two">基础配置</h2><p data-key="62cd82f731866300123e84bd" data-type="paragraph">修改 <span style="color: #e62412">_config.yml</span> 中的网站基础配置，如下：</p><img data-key="62ce93fcf0324900126699ed" data-type="image" src="./62ce93fcf0324900126699ed.png" alt="image.png"><p data-key="62cd820231866300123e84ba" data-type="paragraph">如果对这些配置有不明白的地方，参考文档：<a data-key="thoughts-779585" data-type="LINK" href="https://hexo.io/docs/configuration.html"><u>https://hexo.io/docs/configuration.html</u></a></p><p data-key="62ce941af0324900126699ef" data-type="paragraph"></p><h2 data-key="62ce9817f032490012669ad6" data-type="header-two"><strong>博客侧边栏目配置</strong></h2><p data-key="62ceac9475d10e001253b523" data-type="paragraph">修改 <span style="color: #e62412">_config.tangyuxian.yml</span> 中的网站个性化配置，如下：</p><img data-key="62cea9b575d10e001253b518" data-type="image" src="./62cea9b575d10e001253b518.png" alt="image.png"><p data-key="62ccf18d5a26fa0012d0756a" data-type="paragraph">在 <span style="color: #e62412">source </span>文件夹下依次新建<span style="color: #e62412">archives.md、about.md、friend.md、download.md</span>四个Markdown文件表示我的四个边栏内容<span style="color: #569CD6">文章归档、关于作者、我的朋友、下载中心</span>，并按上图所示修改<span style="color: #569CD6">menu配置</span>，编译后如图所示：</p><img data-key="62ceac4475d10e001253b521" data-type="image" src="./62ceac4475d10e001253b521.png" alt="image.png"><p data-key="62ceac2675d10e001253b520" data-type="paragraph"></p><h2 data-key="62ceaf4b75d10e001253b528" data-type="header-two">个人相关链接配置</h2><p data-key="62ceafb475d10e001253b52d" data-type="paragraph">由于我的其他相关网站比较少，所以这里只配置了一个GitHub，其他的注释处理：</p><img data-key="62ceaf0f75d10e001253b527" data-type="image" src="./62ceaf0f75d10e001253b527.png" alt="image.png"><p data-key="62ceaef175d10e001253b526" data-type="paragraph">实际效果：</p><img data-key="62ceaf8c75d10e001253b52b" data-type="image" src="./62ceaf8c75d10e001253b52b.png" alt="image.png"><p data-key="62ceaf8c75d10e001253b52c" data-type="paragraph"></p><p data-key="62ceafd275d10e001253b52e" data-type="paragraph">配置相关的介绍就到这里，还有其他许多的配置可以自定义，这些内容在配置文件中都有注释，包括相关文档，非常详尽，大家可以自行探索。</p><p data-key="62ceb00e75d10e001253b52f" data-type="paragraph"></p><p data-key="62ccf0f75a26fa0012d07563" data-type="paragraph"></p><p data-key="62ccf0f75a26fa0012d07564" data-type="paragraph"></p><p data-key="62ccf0f75a26fa0012d07565" data-type="paragraph"><br></p></div>

        <footer>
            <a href="https://thoughts.teambition.com/" target="_blank">Thoughts</a>
        </footer>
    

</body></html>
