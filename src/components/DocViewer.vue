<template>
    <div>
        <h1>DocViewer</h1>
    </div>
</template>

<script>
let pdfjs = null

import('pdfjs-dist/webpack')
    .then(pdfjslib => {
        pdfjs = pdfjslib
    })

let pdfjsViewer = null

import ('pdfjs-dist/web/pdf_viewer')
    .then(pdfjsViewerLib => {
        pdfjsViewer = pdfjsViewerLib
    })

export default {
    name: 'DocViewer',

    props: {
        url: String
    },

    data () {
        return {
            pdfjs: pdfjs,
            pdfjsViewer: pdfjsViewer
        }
    }
}
</script>

<style lang="scss" scoped>

</style>