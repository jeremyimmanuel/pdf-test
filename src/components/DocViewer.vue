<template>
    <div>
        <h1>DocViewer</h1>
    </div>
</template>

<script>
// import range from 'lodash/range'

export default {
    name: 'DocViewer',

    props: {
        url: String
    },

    data () {
        return {
            pdfjsLocal: null,
            pdfjsViewerLocal: null,

            pdfDoc: null,
            pages: []
        }
    },

    async created () {
        await this.fetchLibraries()
        await this.fetchPdf()
    },

    methods: {
        async fetchLibraries () {
            const pdfjs = await import('pdfjs-dist/webpack')
            this.pdfjsLocal = pdfjs
            const pdfjsViewer = await import('pdfjs-dist/web/pdf_viewer')
            this.pdfjsViewerLocal = pdfjsViewer
        },

        async fetchPdf () {
            const pdfLoadingTask = await this.pdfjsLocal.getDocument(this.url)
            this.pdfDoc = await pdfLoadingTask.promise
            console.dir(this.pdfDoc)
        }
    }
}
</script>

<style lang="scss" scoped>

</style>