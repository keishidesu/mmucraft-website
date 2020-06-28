# MMUCraft Official Website
This website is written using Nuxt.js 

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```
For detailed explanation, check out [Nuxt.js docs](https://nuxtjs.org).

## Coding style

- Use 2 spaces as indentation
- Logical variable names

## CSS
*Minimize the use of css. Make good use of BootstrapVue or Bootstrap instead for non-complexed designs. <br>
If you are unfamiliar with Bootstrap, this is the [documentation](https://getbootstrap.com/docs/4.3/getting-started/introduction/) for Bootstrap 4 and the [documentation](https://bootstrap-vue.org/docs) for BootstrapVue*

- Define CSS __only__ at `layouts` and `components`
- Only define CSS classes when necessary and try make them re-usable

## Pages
Pages can __only__ include components. For example:

```
mypage.vue (~/pages/mypage.vue)

<template>
  <div>
    <component1 />
    <component2 />
  </div>
</template>
```

## Components

Make __re-usable__ components. 
If the components are only meant for the page itself, create a folder with the same name as the page under `components` and locate your component in there.
For example:

`mycomponent.vue` is a component specifically made for the page `mypage.vue`. <br>
Then locate `mycomponent.vue` in `~/components/mypage/mycomponent.vue`
