<script>
    import { onMount } from "svelte";

    onMount(() => {
        // Check if particlesJS is already loaded
        // @ts-ignore
        if (window.particlesJS) {
            initParticles();
        } else {
            // Load particles.js from CDN
            const script = document.createElement("script");
            script.src =
                "https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js";
            script.onload = () => initParticles();
            document.head.appendChild(script);
        }
    });

    const defaultConfig = {
        particles: {
            number: {
                value: 80,
                density: { enable: true, value_area: 800 },
            },
            color: { value: "#ffffff" },
            shape: { type: "circle" },
            opacity: { value: 0.5, random: true },
            size: { value: 3, random: true },
            line_linked: {
                enable: true,
                distance: 150,
                color: "#ffffff",
                opacity: 0.4,
                width: 1,
            },
            move: {
                enable: true,
                speed: 2,
                direction: "none",
                random: true,
                straight: false,
                out_mode: "out",
            },
        },
        interactivity: {
            detect_on: "canvas",
            events: {
                onhover: { enable: true, mode: "grab" },
                onclick: { enable: true, mode: "push" },
                resize: true,
            },
        },
        retina_detect: true,
    };

    const particlesConfig = {
        particles: {
            number: {
                value: 100,
                density: {
                    enable: false, // Disable density for controlled positioning
                },
            },
            color: {
                value: "#ffffff",
            },
            shape: {
                type: "circle",
            },
            opacity: {
                value: 0.7,
                random: true,
                anim: {
                    enable: true,
                    speed: 1,
                    opacity_min: 0.1,
                    sync: false,
                },
            },
            size: {
                value: 3,
                random: true,
            },
            line_linked: {
                enable: false,
            },
            move: {
                enable: true,
                speed: 6,
                direction: "top-right",
                random: false,
                straight: true,
                out_mode: "out",
                attract: {
                    enable: false,
                },
            },
            // Position particles initially in bottom-left corner
            position: {
                bottom_left: {
                    x: 0,
                    y: 0,
                },
            },
        },
        interactivity: {
            detect_on: "canvas",
            events: {
                onhover: {
                    enable: false,
                },
                onclick: {
                    enable: false,
                },
                resize: true,
            },
        },
        retina_detect: true,
    };

    function initParticles() {
        // @ts-ignore
        particlesJS("particles-background", particlesConfig);
    }
</script>

<div id="particles-background" class="particles-container" />

<style>
    .particles-container {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: -1;
        background: var(--default-bg);
    }
</style>
