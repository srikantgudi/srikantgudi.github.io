<script>
import ResumeItem from "./ResumeItem.svelte";

    let profiles = [
        'Senior software professional with over 20 years of experience',
        '2005 - 2013: Web development experience using PHP, MySQL',
        '2014 onwards into UI development. Skills used Angular, React, Svelte, Stencil, NodeJs, MySql',
        'Can create wire-frames, POCs'
    ];
</script>

<style>
    .text {
        font-family: Montserrat;
        font-size: 16px;
    }
</style>

<ResumeItem>
    <div slot="header">
        Profile
    </div>
    <div slot="content">
        <ul class='text'>
            {#each profiles as line}
                <li>{line}</li>
            {/each}
        </ul>
    </div>
</ResumeItem>