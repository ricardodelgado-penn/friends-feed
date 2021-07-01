<script>
    export let increaseCount
    export let decreaseCount

    const click = () => {
        selected ? decreaseCount() : increaseCount()

        selected = !selected
    }

    let selected = false
</script>

<span class="tu-icon {selected ? 'selected' : 'deselected'}" on:click={click}>
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16">
        <g fill="none" fill-rule="evenodd">
            <g fill={selected ? "#C58E01" : "#d6d6d6" }>
                <g>
                    <g>
                        <g>
                            <path d="M14 6H8V2c0-1.2-.8-2-2-2L3 7H1c-.6 0-1 .4-1 1v7c0 .6.4 1 1 1h11c1.4 0 2.7-1 2.9-2.4l1-5.2C16.2 7.2 15.3 6 14 6z" transform="translate(-32.000000, -389.000000) translate(16.000000, 250.000000) translate(16.000000, 138.000000) translate(-0.000000, 1.000000)"/>
                        </g>
                    </g>
                </g>
            </g>
        </g>
    </svg>
</span>

<style>
    .selected {
        animation: bump 300ms;
        transform: scale(1);
    }

    @keyframes bump {
        from {
            transform: scale(1);
        }

        50% {
            transform: scale(1.2);
        }

        to {
            transform: scale(1);
        }
    }
</style>
