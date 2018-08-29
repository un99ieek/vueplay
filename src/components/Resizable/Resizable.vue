<template>
  <div>
    <table>
      <thead>
        <tr>
          <th><div class="resizable">111</div></th>
          <th><div class="resizable">222</div></th>
          <th><div>333</div></th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>one</td>
          <td>two</td>
          <td>three</td>
  </tr>
        <tr>
          <td>four</td>
          <td>five</td>
          <td>six</td>
        </tr>
        <tr>
          <td>seven</td>
          <td>eight</td>
          <td>nine</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
// (function () {
//   var thElm
//   var startOffset

//   Array.prototype.forEach.call(
//     document.querySelectorAll('table th'),
//     function (th) {
//       console.log(th)
//       th.style.position = 'relative'

//       var grip = document.createElement('div')
//       grip.innerHTML = '&nbsp;'
//       grip.style.top = 0
//       grip.style.right = 0
//       grip.style.bottom = 0
//       grip.style.width = '5px'
//       grip.style.position = 'absolute'
//       grip.style.cursor = 'col-resize'
//       grip.addEventListener('mousedown', function (e) {
//         thElm = th
//         startOffset = th.offsetWidth - e.pageX
//       })

//       th.appendChild(grip)
//     })

//   document.addEventListener('mousemove', function (e) {
//     if (thElm) {
//       thElm.style.width = startOffset + e.pageX + 'px'
//     }
//   })

//   document.addEventListener('mouseup', function () {
//     thElm = undefined
//   })
// })()
export default {
  name: 'Resizable'
}
</script>
<style>
table {
  border-collapse: collapse;
  border-spacing: 0px;
}
td {
  border: 1px solid black;
  padding: 0;
  margin: 0px;
  overflow: auto;
}

th {
  background-color: yellow;
  padding: 0;
  margin: 0px;
  border: 1px solid black;
}

table th div {
  /* resize: horizontal; */
  overflow: auto;
  width: 120px;
  height: 20px;
  margin: 0px;
  padding: 0px;
  border: 0px solid black;
  display:block;
}

table th div.resizable {
  resize: horizontal;
  cursor: col-resize;
}

th div {
  border: 0;
  width: auto;
  height: fixed;
  min-height: 20px;
  min-width: 20px;
}
</style>
