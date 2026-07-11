<p align="center"><img src="https://raw.githubusercontent.com/go-lemmy/brand/main/social/go-lemmy.png" alt="go-lemmy" width="640"></p>

<h1 align="center">go-lemmy</h1>
<p align="center">Pure-Go read client for the Lemmy REST API.</p>
<p align="center"><a href="https://go-lemmy.github.io/docs/"><img src="https://img.shields.io/badge/docs-mkdocs--material-0A6E96?style=flat-square&logo=materialformkdocs&logoColor=white" alt="docs"></a> <a href="https://pkg.go.dev/github.com/go-lemmy/lemmy"><img src="https://img.shields.io/badge/pkg.go.dev-reference-0079A8?style=flat-square&logo=go&logoColor=white" alt="pkg.go.dev"></a> <img src="https://img.shields.io/badge/Go-1.26-00ADD8?style=flat-square&logo=go&logoColor=white" alt="Go"> <img src="https://img.shields.io/badge/license-BSD--3--Clause-0A6E96?style=flat-square" alt="license"></p>

---

## What is this?

A pure-Go (**CGO=0**), dependency-free read client for the [Lemmy](https://join-lemmy.org/) REST API (`/api/v3`). Point it at any Lemmy instance and read its communities and posts. An optional `Login` stores a JWT for authenticated reads. Standard library only; builds for all 64-bit targets.

The client lives in [`go-lemmy/lemmy`](https://github.com/go-lemmy/lemmy):

```go
c := lemmy.New("https://lemmy.world")

list, err := c.Posts(context.Background(), lemmy.PostsOptions{
	Community: "technology", Sort: "Hot", Limit: 20,
})
if err != nil {
	panic(err)
}
for _, p := range list.Posts {
	fmt.Printf("%s — %s (score %d)\n", p.Title, p.Community, p.Score)
}
```

## Install

```sh
go get github.com/go-lemmy/lemmy
```

## Links

- 📖 Docs — <https://go-lemmy.github.io/docs/>
- 🌐 Site — <https://go-lemmy.github.io/>
- 🧩 Client — <https://github.com/go-lemmy/lemmy>
- 📦 API reference — <https://pkg.go.dev/github.com/go-lemmy/lemmy>
- 🎨 Brand assets — <https://github.com/go-lemmy/brand>

---
<p align="center"><sub>Branding in <a href="https://github.com/go-lemmy/brand">go-lemmy/brand</a>.</sub></p>
