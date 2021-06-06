<script>
  import { addMessages, init, getLocaleFromNavigator /*, register */ } from 'svelte-intl-precompile';
  import en from '../../locales/en.js';
	import { t } from 'svelte-intl-precompile'

  // @ts-ignore
  addMessages('en', en);
  // register('es', () => import('../../locales/en.js')); <-- use this approach if you want locales to be load lazily

  init({
    fallbackLocale: 'en',
    initialLocale: getLocaleFromNavigator()
  });
  let count = 0;
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<p>{$t("foot", { values: { count: count } })}</p>
<button type="button" on:click={() => count++}>Increment count</button>
<button type="button" on:click={() => count--}>Increment count</button>
