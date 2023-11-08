<script setup>

</script>

<template>
    <div class="flex justify-center">
        <div class="card p-4 rounded shadow-lg py-2">

                <div id="card-header">
                <slot name="header"></slot>
                <hr>
                </div>
                <div id="card-content">
                    <slot></slot>
                </div>
                <div id="card-footer">
                    <slot name="footer"></slot>
                </div>

        </div>

    </div>
</template>
