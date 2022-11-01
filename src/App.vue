<template>
  <router-view />
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,200;0,300;0,400;0,500;0,600;0,700;0,800;1,200;1,300;1,400;1,500;1,600;1,700;1,800&display=swap');
/* font-family: 'Plus Jakarta Sans', sans-serif; */

*, *::before, *::after {
  box-sizing: border-box;
}
* {
  margin: 0;
}
html, body {
  height: 100%;
  font-family: 'Plus Jakarta Sans', sans-serif;
}
body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
}
img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
}
input, button, textarea, select {
  font: inherit;
}
p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}
#root, #__next {
  isolation: isolate;
}

:root{
  /* primary */
  --red: hsl(1, 90%, 64%);
  --blue: hsl(219, 85%, 26%);

  /* neutral */
  --white: hsl(0, 0%, 100%);
  --vlgblue: hsl(210, 60%, 98%);
  --lgblue1: hsl(211, 68%, 94%);
  --lgblue2: hsl(205, 33%, 90%);
  --gblue: hsl(219, 14%, 63%);
  --dgblue: hsl(219, 12%, 42%);
  --vdblue: hsl(224, 21%, 14%);
}
</style>
