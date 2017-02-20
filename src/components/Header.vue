<template>
    <div class="row">
        <h3>Quotes Added</h3>
        <div class="col-sm-12">
            <div class="progress">
                <div :style="{width: (quoteCount / maxQuotes) * 100 + '%'}" class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100">
                    {{ quoteCount }} / {{ maxQuotes }}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['quoteCount', 'maxQuotes']
    }
</script>
 