<script>
  import { base } from "$app/paths";
    import { check_outros } from "svelte/internal";

  //UBERCHORDS SDK
  // (function(d, s, id) {
  // var js, ucjs = d.getElementsByTagName(s)[0];
  // if (d.getElementById(id)) return;
  // js = d.createElement(s); js.id = id;
  // js.src = "//static.uberchord.com/uberchord-embed-sdk.js";
  // ucjs.parentNode.insertBefore(js, ucjs);
  // }(document, 'script', 'uberchord-jssdk'));
  //Ends Here

  const UberChordAPI = "https://api.uberchord.com/v1/embed/"
  const Chords = "chords"
  const EMDED = "embed/"
  const SearchPrefix = "?nameLike="

  const validateForm = (params) => {
    console.log("Validating a Form")
    // console.log(params)
  }

  const submitForm = () => {
    let searchValue = document.getElementById("searchBox").value
    console.log(searchValue)
    let myIframe = document.querySelector("iframe")
    myIframe["src"] = `${UberChordAPI}${Chords}${SearchPrefix}${searchValue}`
  }
</script>

<nav>
  <h1>TarChords</h1>
  <p>Google for guitar chords</p>
  <form on:submit|preventDefault={validateForm}>
    <input type=search id="searchBox">
    <input type=submit on:click={submitForm}>
  </form>
</nav>
<section id="chordSpace">
  <iframe title="Chords" src="https://api.uberchord.com/v1/embed/chords?nameLike=F"></iframe>
</section>

<!-- <h1>sveltekit-gh-pages</h1>
<p>Deployed to GitHub Pages</p>
<p>
  Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation
</p>
<a href="{base}/about">About</a> -->
