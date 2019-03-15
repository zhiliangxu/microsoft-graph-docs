<div
  style="
display: flex; 
flex-direction: column;
width: 512px;
"
>
  <div
    style="
  display: flex;
  flex-direction: row;
  width: 512px;
  height: 30px;
  background-color: #f2f2f2;
  border: 1px solid #ececec;
  border-bottom: none;
  justify-content: space-between;
  "
  >
    <div style="margin: 5px 0 0 5px;">Graph Explorer</div>
    <div>
      <input
        style="background-color: #128712; color: white; border: none; height: 100%;"
        type="button"
        onClick="showIframe()"
        value="Try It"
      />
    </div>
  </div>
  <div
    style=" display: flex; width: 100%; padding: 5px; border: 1px solid #ececec; background-color: #fafafa;"
  >
    <p>https://graph.microsoft.com/v1.0/me/messages</p>
  </div>
</div>

<div id='ge-iframe'>
</div>
<script>
  function attachIframe(url) {
    var iframeNode = `<iframe id='myIframe' height='900px'
     scrolling='no' title='Toolkit Test embedded' 
     src='http://localhost:3000#${url}'
     frameborder='no' allowtransparency='true' allowfullscreen='true' 
     style='width: 100%; visibility: hidden'>See the code: .</iframe>`
    var iframeContainer = document.getElementById('ge-iframe')
    iframeContainer.innerHTML = iframeNode;
  }
  
  attachIframe('https://graph.microsoft.com/v1.0/me/messages')
  function showIframe() {
    var myIframe = document.getElementById('myIframe');
    myIframe.style['visibility']='visible'
  }
</script




