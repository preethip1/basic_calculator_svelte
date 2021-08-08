<script>
    let clicked = "";
    let total = "";
    function onNumberClick(number) {
        if (number === "=") {
            try {
                total = eval(clicked);
            } catch (error) {
                total = "error";
            }
        } else {
            clicked = clicked + number;
        }
    }
    function onClear() {
        clicked = "";
        total = "";
    }
    function onDelete() {
        clicked = clicked.slice(0, -1);
    }
</script>

<div class="h-auto w-80 flex flex-col border-2 border-gray-300 bg-gray-300">
    {#if total == ""}
        <input
            bind:value={clicked}
            class="flex-auto h-10 w-full border-2 bg-white p-2"
        />
    {:else}
        <input
            bind:value={total}
            class="flex-auto h-10 w-full border-2 bg-white p-2"
        />
    {/if}
    <div class="flex-auto h-auto w-full flex flex-row">
        <button
            on:click={onClear}
            class="flex flex-grow m-1 p-1 justify-center items-center bg-white"
            >Clear</button
        >
        <button
            on:click={onDelete}
            class="flex flex-grow m-1 p-1 justify-center items-center bg-white"
            >Delete</button
        >
    </div>
    <div class="flex-auto">
        <div class="flex flex-col">
            <div class="flex flex-row justify-center items-center">
                <div
                    on:click={() => onNumberClick("7")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    7
                </div>
                <div
                    on:click={() => onNumberClick("8")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    8
                </div>
                <div
                    on:click={() => onNumberClick("9")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    9
                </div>
                <div
                    on:click={() => onNumberClick("/")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    /
                </div>
            </div>
            <div class="flex flex-row justify-center items-center">
                <div
                    on:click={() => onNumberClick("4")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    4
                </div>
                <div
                    on:click={() => onNumberClick("5")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    5
                </div>
                <div
                    on:click={() => onNumberClick("6")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    6
                </div>
                <div
                    on:click={() => onNumberClick("-")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    -
                </div>
            </div>
            <div class="flex flex-row justify-center items-center">
                <div
                    on:click={() => onNumberClick("1")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    1
                </div>
                <div
                    on:click={() => onNumberClick("2")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    2
                </div>
                <div
                    on:click={() => onNumberClick("3")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    3
                </div>
                <div
                    on:click={() => onNumberClick("+")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    +
                </div>
            </div>
            <div class="flex flex-row justify-center items-center">
                <div
                    on:click={() => onNumberClick("0")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    0
                </div>
                <div
                    on:click={() => onNumberClick(".")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    .
                </div>
                <div
                    on:click={() => {
                        onNumberClick("=");
                    }}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    =
                </div>
                <div
                    on:click={() => onNumberClick("x")}
                    class="flex-auto m-2 p-2 bg-white text-center"
                >
                    x
                </div>
            </div>
        </div>
    </div>
</div>
