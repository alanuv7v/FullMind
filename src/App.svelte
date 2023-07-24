<!-- UI 라이브러리 참고: https://joyofcode.xyz/svelte-ui-libraries
특히 요거 맘에듬 https://carbon-components-svelte.onrender.com/components/Tooltip
그 외
https://illright.github.io/attractions//docs/components/text-field
https://daisyui.com/components/

라이브러리의 장점은 잘 알겠다. 그러나 단점이 있다면?:
https://armadillo-dev.github.io/ui/ux/benefit-and-cost-of-ui-component-framework/

...결국 CSS가 중요한 상황이 오기 전까진 일단 쓰지 말자.
로직부터 짜고, 나중에 생각하자. UI 라이브러리는 미관을 고려할 때 사용하자. 지금은 미관은 제껴두자.

-->

<script>
  import {setContext} from "svelte"
  import Container from "./Container.svelte"

  let containers = [1,2,3,4,5]

  
  function createNewContainer() {
    alert("triggered")
    containers.push("a")
  }

  setContext('createNewContainer', createNewContainer)

</script>

<main>
  <div id="header">FullMind</div>
  <div id="content">
    {#each containers as container, index(container)}
      <Container {container}/>
    {/each}
  </div>
  
</main>


<style>
  main {
    height: 800px;
  }
  #content {
    border: 4px solid lightgray;
    height: 100%;

  }
</style>


