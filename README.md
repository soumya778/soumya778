<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <!-- <meta name="theme-color" content="#00D494"> -->
    <title>Home Page</title>
    <link rel="stylesheet" type="text/css" href="assets/css/style.css" />
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
      integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T"
      crossorigin="anonymous"
    />
    <!-- <link rel="manifest" href="/manifest.json"> -->
   
    <style type="text/css" media="screen">
      body {
        overflow: hidden;
      }

      #editor {
        min-width: 500px;
        min-height: 500px;
      }
    </style>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script
      src="src-noconflict/ace.js"
      type="text/javascript"
      charset="utf-8"
    ></script>
  </head>
  <body>
   
    <div>
      <h1>Code Editor</h1>
      <select id="myselect" onchange="onSelectChange(this.value.trim())">
        <option value="53" >C++</option>
        <option value="62" >Java</option>
        <option value="70">Python</option>
      </select>
      <form method="post" action=
      "https://www.jdoodle.com/api/redirect-to-post/compiler_URL">
          <textarea name="initScript"
              rows="8" cols="80">
          </textarea>
          
          <input type="submit" value="Execute">
      </form>
      <div id="editorContainer">
        <div class="container" style="margin-top: 30px">
          <div class="row">
            <div class="col">
              <pre id="editor">
      </pre
              >
            </div>
            <div class="col">
              <button class="btn btn-success">Output</button>
              <br />
              <pre id="ans"></pre>
            </div>
          </div>
        </div>
      </div>
    </div>
    <script src="texteditor.js"></script>
    <script>
        

      function onSelectChange(selectedVal){
       
    console.log(selectedVal)
        if(selectedVal != undefined && selectedVal!=null && selectedVal!=""){
         $("button").off('click');
          codeEditor(selectedVal)
        }
      }
      window.onload = function () {
          codeEditor("53");
      };
    </script>
  </body>
</html>
