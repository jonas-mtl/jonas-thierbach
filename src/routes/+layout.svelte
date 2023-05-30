<script lang="ts">
    // Icon imports
    import Icon from 'svelte-icons-pack/Icon.svelte';
    import FaSolidHome from "svelte-icons-pack/fa/FaSolidHome";
    import IoSchool from "svelte-icons-pack/io/IoSchool";

    import '$lib/styles/layout.scss'
</script>

<section class="sidebar">
    <div class="sidebar-container">
        <div class="profile">
            <h1>Jonas</h1>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. </p>
        
            <nav>
                <ul>
                    <li><Icon src={FaSolidHome} /> <a href="/">Home</a></li>
                    <li><Icon src={IoSchool} /> <a href="/schule">Schule</a></li>
                </ul>
            </nav>
        </div>
    
        <footer>
            <ul>
                <li>Github</li>
            </ul>
        </footer>
    </div>
</section>
<slot />