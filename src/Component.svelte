<script>
  import { getContext } from "svelte"

  const { styleable } = getContext("sdk")
  const component = getContext("component")
  export let url = '';
  let result;

  async function getEmbedURL (url) {
    const res = await fetch(url)
    const json = await res.json()
    return json
  }

  $: result = getEmbedURL(url);
</script>

<div use:styleable={$component.styles}>
  <div>
    result
  </div>
</div>