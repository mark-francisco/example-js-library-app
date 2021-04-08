<template>
  <div class="about">
    <h1>This is an about page</h1>
    Contact me at:
    <p>
      <span id="email"><strong>mark@example.com</strong></span>
    </p>
    <button class="btn-to-click" data-clipboard-target="#email">copy e-mail</button>

    <hr />
    <!-- Target -->
    <p>
      <input id="text-to-copy" value="https://github.com/zenorocha/clipboard.js.git" />
    </p>
    <!-- Trigger -->
    <button class="btn-to-click" data-clipboard-target="#text-to-copy">Copy to Clipboard!</button>
  </div>
</template>
<style></style>
<script>
// couldn't get the ES6 "import" syntax to work, so had to use this ES5 syntax
var ClipboardJS = require("clipboard");

// 3. Instantiate clipboard by passing a string selector
var clipboard = new ClipboardJS(".btn-to-click");

clipboard.on("success", function (e) {
  console.log(e);

  // clear the highlighting from the input box
  e.clearSelection();
});

clipboard.on("error", function (e) {
  console.log(e);
});
</script>
