<template>
  <component :is="type" class="index">
    <nav-bar active="Index" :navItems="[
      {name: 'Template', component: 'Index', href: '/#/'},
      {name: 'Living Docs', href: 'http://localhost:6060/'}
    ]"/>
    <wrapper>
      <heading level="h1">Method Design System</heading>
      <text-style><a href="https://vueds.com">Method Design System</a> is the single source of design truth at Method Studios. The system contains the tools, patterns &amp; practices to make cutting-edge projects. It works as the foundation of all systems development.</text-style>
      <v-card height="200px" flat>
        <div class="headline text-xs-center pa-5">Active: {{ e1 }}</div>
        <v-bottom-nav absolute :value="true" :active.sync="e1" color="transparent">
          <v-btn flat color="teal" value="recent">
            <span>Recent</span>
            <v-icon>history</v-icon>
          </v-btn>
          <v-btn flat color="teal" value="favorites">
            <span>Favorites</span>
            <v-icon>favorite</v-icon>
          </v-btn>
          <v-btn flat color="teal" value="nearby">
            <span>Nearby</span>
            <v-icon>place</v-icon>
          </v-btn>
        </v-bottom-nav>
      </v-card>
    </wrapper>
  </component>
</template>

<script>
/**
 * Shows how to layout and structure a home page.
 */
export default {
  name: "Index",
  status: "deprecated",
  release: "1.0.0",
  metaInfo: {
    title: "Method Design System",
    htmlAttrs: {
      lang: "en",
    },
  },
  props: {
    /**
     * The html element name used for the component.
     */
    type: {
      type: String,
      default: "div",
    },
  },
}
</script>

<style lang="scss" scoped>
// Design Tokens with local scope
$color-template-background: $color-rich-black;
$color-template-background-top: tint($color-template-background, 5%);
$color-template-background-bottom: shade($color-template-background, 5%);
$color-template-text: $color-white;
$color-template-link: $color-bleu-de-france;

.index {
  @include reset;
  @include inset-space($space-base);
  min-height: $space-xx-large * 4;
  background: $color-template-background;
  background: linear-gradient(0deg, $color-template-background-bottom, $color-template-background-top 100%);
  text-align: center;
  position: relative;
  float: left;
  height: 100%;
  width: 100%;
  @media #{$media-query-large} {
    // This is how you’d use design tokens with media queries
  }
  .heading {
    color: $color-template-text;
  }
  .text-style {
    color: $color-template-text;
  }
  .text-link {
    color: $color-template-link;
  }
  .wrapper {
    max-width: $space-xx-large * 4.5;
    transform: translateX(-50%) translateY(-50%);
    position: absolute;
    left: 50%;
    top: 50%;
  }
  a {
    font-family: $font-family-text;
    color: $color-bleu-de-france;
    text-decoration: underline;
  }
}
</style>

<docs>
  ```jsx
  <index />
  ```
</docs>
