<script>
	import { page } from '$app/stores';
	import github from '$lib/images/github.svg';
</script>

<footer>
  <div class="corner">
    <p>by<a href="https://x.com/datsuns">@datsuns</a></p>
    <a href="https://github.com/datsuns/nurusaba-watcher">
      <img src={github} alt="GitHub" />
    </a>
  </div>
</footer>

<style>
	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 5px;
	}

	footer a{
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

  footer a img {
		width: 4em;
		height: 4em;
		object-fit: contain;
  }
</style>
