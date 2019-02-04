# Trying [Cactus](https://github.com/ostera/cactus)

## Installing

```sh
opam pin --dev omd
opam pin add cactus https://github.com/ostera/cactus.git
```

## Getting Started

Cactus works in a very simple way. In fact it's almost silly how simple it is. If you put a cactus-project file on the root of your project, cactus will look throughout your whole project for site files.

site files simply tell cactus that this particular folder should be compiled into a website.

So if you have your posts in the following structure:

```sh
➜  cactus-example tree
.
├── README.md
├── pages
│   ├── First-post.md
│   └── Some-other-post.md
└── sections
    ├── about.md
    ├── hire-me.md
    └── projects.md
```

You just need to touch a few files:

```sh
➜  cactus-example touch cactus-project
➜  cactus-example touch pages/site sections/site
```

Which gets you this tree:

```sh
➜  cactus-example tree
.
├── README.md
├── cactus-project
├── pages
│   ├── First-post.md
│   ├── Some-other-post.md
│   └── site
└── sections
    ├── about.md
    ├── hire-me.md
    ├── projects.md
    └── site

2 directories, 9 files
```

And you can run `cactus build` to compile the website using the same tree structure under a _public folder:

```sh
➜  cactus-example cactus build
🌵 Compiling project...
🌮 Done with 8 targets in 0.025s
➜  cactus-example tree
.
├── README.md
├── _public
│   ├── pages
│   │   ├── First-post.html
│   │   └── Some-other-post.html
│   └── sections
│       ├── about.html
│       ├── hire-me.html
│       └── projects.html
├── cactus-project
├── pages
│   ├── First-post.md
│   ├── Some-other-post.md
│   └── site
└── sections
    ├── about.md
    ├── hire-me.md
    ├── projects.md
    └── site

5 directories, 14 files
```

Let try deploying with `Now`.
`cd _public && now --public`
Here is the link: <https://public-hfxpuofntn.now.sh>

