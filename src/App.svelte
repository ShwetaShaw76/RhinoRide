<script>
    import {Router, link, Route} from 'svelte-routing';
    import Home from './Home.svelte';
    import Squishy from './Squishy.svelte';

    export let url ="";
</script>
<Router {url}>
  <div>
    <Route path="/Squishy"><Squishy /></Route>
    <Route path="/"><Home /></Route>
  </div>
</Router>
