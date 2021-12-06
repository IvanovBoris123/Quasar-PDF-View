<template>
  <div class="container">
    <!-- <button type="button" class="btn btn-primary" @click=view_pdf()>Open</button>
    <q-page-container id="pdfContainer"></q-page-container> -->
    <div class="row">
      <div class="col-md-2"><button type="button" class="btn btn-primary" @click=view_pdf()>Open</button></div>
      <div class="col-md-8" id="pdfContainer"></div>
      <div class="col-md-2">abs</div>
    </div>
  </div>
</template>

<script>
import { PdfViewerControl } from '@accusoft/pdf-viewer'
import '../assets/bootstrap.min.css'

export default {
  name: 'PDFView',
  // mounted: function () {
  //   (async () => {
  //     window.myViewer = await PdfViewerControl.create({
  //       container: document.getElementById('pdfContainer'),
  //       sourceDocument  : 'bioSketch.pdf'
  //     });
  //   })();
  // }
  methods: {
    view_pdf: () => {
      (async () => {
        window.myViewer = await PdfViewerControl.create({
          container: document.getElementById('pdfContainer'),
          sourceDocument  : 'bioSketch.pdf',
            licenseKey: 'MIT', // or 'eval'
            allowedControls: {
              lineTool: true,
              search: false
            }
        });
      })();
    }
  }
}
</script>

