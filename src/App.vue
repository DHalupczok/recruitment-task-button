<script setup lang="ts">
import { RouterView } from 'vue-router'
import CustomButton from '@/components/CustomButton.vue'
import SupportIcon from '@/components/icons/IconSupport.vue'
</script>

<template>
  <header>
    <RouterView />
  </header>
  <main>
    <div>
      <p>#Be able to be displayed as button, a or router-link</p>
      <custom-button @smash="() => console.log($route)" class="btn-primary"
        >Primary button
      </custom-button>
      <custom-button href="about:blank" class="btn-primary">Primary link</custom-button>
      <custom-button v-if="$route.path === '/'" to="/about" class="btn-primary"
        >Primary router link (about)
      </custom-button>
      <custom-button class="btn-primary" to="/" v-else>Primary router link (home)</custom-button>
    </div>
    <div>
      <p>
        Comes in 3 sizes (each button style regardless of variant stylistic has the same
        dimensions): small, regular(default), large
      </p>
      <p>
        <custom-button class="btn-primary btn-large">Primary button large</custom-button>
        <custom-button class="btn-secondary btn-large">Secondary button large</custom-button>
      </p>
      <p>
        <custom-button class="btn-primary">Primary button regular</custom-button>
        <custom-button class="btn-secondary">Secondary button regular</custom-button>
      </p>
      <p>
        <custom-button class="btn-primary btn-small">Primary button small</custom-button>
        <custom-button class="btn-secondary btn-small">Secondary button small</custom-button>
      </p>
    </div>
    <div>
      <p>Comes in 2 stylistic variants: filled (default), outlined</p>
      <p>
        <custom-button class="btn-primary">Primary filled</custom-button>
        <custom-button class="btn-primary btn-outline">Primary outline</custom-button>
      </p>
      <p>
        <custom-button class="btn-secondary">Secondary filled</custom-button>
        <custom-button class="btn-secondary btn-outline">Secondary outline</custom-button>
      </p>
      <p>
        <custom-button class="btn-danger">Danger filled</custom-button>
        <custom-button class="btn-danger btn-outline">Danger outline</custom-button>
      </p>
      <p>
        <custom-button class="btn-warning">Warning filled</custom-button>
        <custom-button class="btn-warning btn-outline">Warning outline</custom-button>
      </p>
      <p>
        <custom-button class="btn-success">Success filled</custom-button>
        <custom-button class="btn-success btn-outline">Success outline</custom-button>
      </p>
    </div>
    <div>
      <p>Has the option of displaying in block mode (100% width + centered horizontal content)</p>
      <custom-button class="btn-success"
        >Regular mode
        <SupportIcon />
      </custom-button>
      <custom-button class="btn-danger" :block-mode="true"
        >Block mode
        <SupportIcon />
      </custom-button>
    </div>
    <div>
      <p>
        Has a disabling option (disabled attribute), which: makes the button not clickable, makes
        the button visually gray and less visible (opacity .4) and no hover or focus effects work
        (not only visually)
      </p>
      <p>
        <custom-button
          @smash="() => console.log(`Enabled button was smashed`)"
          class="btn-secondary"
          >Secondary button
        </custom-button>
        <custom-button
          @smash="() => console.warn('Disabled button was smashed!!!')"
          class="btn-secondary"
          :disabled="true"
          >Secondary button disabled
        </custom-button>
      </p>
      <p>
        <custom-button href="about:blank" class="btn-danger">Danger link</custom-button>
        <custom-button class="btn-danger" href="about:blank" :disabled="true"
          >Danger link disabled
        </custom-button>
      </p>
      <p>
        <custom-button to="about" class="btn-warning">Warning router link</custom-button>
        <custom-button to="about" class="btn-warning" :disabled="true"
          >Warning router link disabled
        </custom-button>
      </p>
    </div>
    <div>
      <p>
        Button content should be limited to one line height + w if you insert elements other than
        text (e.g. image/icon) should be centered vertically to each other
      </p>
      <custom-button class="btn-success"
        >Love me
        <SupportIcon />
      </custom-button>
    </div>
    <div>
      <p>
        Buttons of the same size next to each other should always have the same size dimension
        (height) regardless of the stylistic variant
      </p>
      <p>
        <custom-button class="btn-danger btn-large">Danger large</custom-button>
        <custom-button class="btn-warning btn-large">Warning large</custom-button>
        <custom-button class="btn-success btn-outline btn-large"
          >Success outline large
        </custom-button>
      </p>
      <p>
        <custom-button class="btn-danger">Danger regular</custom-button>
        <custom-button class="btn-warning">Warning regular</custom-button>
        <custom-button class="btn-success btn-outline">Success outline regular</custom-button>
      </p>
      <p>
        <custom-button class="btn-danger btn-small">Danger small</custom-button>
        <custom-button class="btn-warning btn-small">Warning small</custom-button>
        <custom-button class="btn-success btn-small btn-outline"
          >Success outline small
        </custom-button>
      </p>
    </div>
    <div>
      <p>
        Buttons of different sizes should always be next to each other centered on the current line:
      </p>
      <custom-button class="btn-warning btn-small">Filled small</custom-button>
      <custom-button class="btn-warning">Filled regular</custom-button>
      <custom-button class="btn-warning btn-large">Filled large</custom-button>
    </div>
    <div>
      <p>
        Report the following events: click - when clicking on a button that is not disabled, the
        event argument should be a native event from the browser
      </p>
      <custom-button class="btn-warning" @smash="(e) => console.warn(e)"
        >Click me and observe the console
      </custom-button>
    </div>
  </main>
</template>

<style scoped>
header {
  position: sticky;
  top: 0;
  z-index: 10;
}

div {
  border-radius: 5px;
  border: var(--info) solid 2px;
  padding: 1rem;
  margin: 1rem;
  background-color: white;
}
</style>
