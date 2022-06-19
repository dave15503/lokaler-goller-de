<script>
    export let menuItems;
    export let title;

    const scrollTo = (href) => {
        const element = document.querySelector(href);
        console.log(element);

        const menu = document.querySelector("#menu");

        const position = element.getBoundingClientRect().top + window.pageYOffset - menu.offsetHeight;

        console.log("scrolling to " + position + " of " + JSON.stringify(element));

        window.scrollTo({
            top: position,
            baviour: "smooth",
        });
    }

    let menuOpen = false;
</script>

 <div class="top-nav" id="menu">
        <div class="nav">
            <h1 class="top-nav-wrap">
                <a href="#start">{title}</a>
            </h1>
            <span class="top-nav-main nav">
                {#each menuItems as menu (menu.id)}
                    {#if menu.link[0] === '#'}
                        <div class="link" on:click={(evt) => scrollTo(menu.link)}>
                            {menu.title}
                        </div>
                    {:else}
                        <a class="link" href={menu.link}>{menu.title}</a>
                    {/if}
                {/each}
            </span>
            <div class="hamburger-menu {menuOpen ? 'active' : ''}" on:click={(evt) => (menuOpen = !menuOpen)}>
                <div />
            </div>
        </div>
        <div class="top-nav-main-vertical {menuOpen ? 'active' : ''}">
            {#each menuItems as menu (menu.id)}
                {#if menu.link[0] === '#'}
                        <div class="link" on:click={(evt) => scrollTo(menu.link)}>
                            {menu.title}
                        </div>
                    {:else}
                        <a class="link" href={menu.link}>{menu.title}</a>
                    {/if}
            {/each}
        </div>
</div>

<style>
  .nav {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    .top-nav-wrap {
        font-size: var(--headline-font-size);
        padding-right: 50px;
        padding-left: 30px;
        margin-top: 5px;
        margin-bottom: 5px;
    }

    .top-nav-main {
        gap: 25px;
        font-size: var(--subheadline-font-size);
    }

    .top-nav {
        position: fixed;
        z-index: 10;
        background-color: var(--background-color);
        width: 100%;
    }

        .hamburger-menu {
        display: none;
        justify-self: end;

        height: 40px;
        width: 40px;

        align-items: center;
        justify-content: center;
    }

    .hamburger-menu > div {
        position: relative;
        top: 0;
        left: 0;
        background: white;
        height: 2px;
        width: 60%;
        transition: all 0.5s ease-in-out;
    }

    .hamburger-menu > div::before,
    .hamburger-menu > div::after {
        content: "";
        position: absolute;
        top: -10px;
        background: white;
        width: 100%;
        height: 2px;
        transition: all 0.5s ease-in-out;
    }

    .hamburger-menu > div::after {
        top: 10px;
    }

    .hamburger-menu.active > div::before {
        transform: rotate(45deg);
        top: 0;
        background: white;
    }
    .hamburger-menu.active > div::after {
        transform: rotate(-45deg);
        top: 0px;
        background: white;
    }

    .hamburger-menu.active > div {
        background: rgba(0, 0, 0, 0);
    }

    .top-nav-main-vertical {
        display: flex;
        overflow: hidden;
        flex-direction: column;
        align-items: center;
        padding-bottom: 5px;
        gap: 5px;
        font-size: var(--subheadline-font-size);
        max-height: 0px;
        transition: max-height 0.5s ease-out;
    }

    @media only screen and (max-width: 800px) {
        .hamburger-menu {
            display: flex;
        }

        .top-nav-main {
            display: none;
        }

        .top-nav > .nav {
            justify-content: space-between;
        }

        .top-nav-main-vertical.active {
            display: flex;
            max-height: 500px;
        }
    }

</style>

