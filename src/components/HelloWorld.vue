<template>
  <div class="text-primary">
    <v-container>
      <quill-editor
        tag-name="textarea"
        v-model="content"
        name="content"
        :editor="editor"
        :config="editorConfig"
        :options="editorOption"
      ></quill-editor>
    </v-container>
  </div>
</template>

<script>
import { quillEditor } from "vue-quill-editor";
import ImageResize from "quill-image-resize-vue";
Quill.register("modules/imageResize", ImageResize);
import { Quill } from "vue2-editor";
export default {
  components: {
    quillEditor,
  },

  data: () => ({
    content: null,
    editor: "",
    showerrmsg: false,
    editorConfig: {
      required: true,
    },
    editorOption: {
      modules: {
        toolbar: [
          ["bold", "italic", "underline", "strike"],
          ["blockquote", "code-block"],
          [{ header: 1 }, { header: 2 }],
          [{ list: "ordered" }, { list: "bullet" }],
          [{ script: "sub" }, { script: "super" }],
          [{ indent: "-1" }, { indent: "+1" }],
          [{ direction: "rtl" }],
          [{ size: ["small", false, "large", "huge"] }],
          [{ header: [1, 2, 3, 4, 5, 6, false] }],
          [{ font: [] }],
          [{ color: [] }, { background: [] }],
          [{ align: [] }],
          ["clean"],
          ["link", "image", "video"],
          ["template-partediario"],
        ],
        imageResize: {
          displayStyles: {
            backgroundColor: "black",
            border: "none",
            color: "white",
          },
          modules: ["Resize", "DisplaySize", "Toolbar"],
        },
      },
    },
  }),
};
</script>

<style>
@import "~quill/dist/quill.core.css";
@import "~quill/dist/quill.snow.css";
@import "~quill/dist/quill.bubble.css";
</style>