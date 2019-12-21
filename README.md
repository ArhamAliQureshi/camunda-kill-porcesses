# camunda-kill-porcesses

var count =5
var timed = 500;
function processEl(el) {
  var el = document.querySelector(".instance-id > span > a");
  el.click();
  setTimeout(() => {
    document.querySelector(".glyphicon-remove").click();
    setTimeout(() => {
      document.querySelectorAll(".btn-primary").forEach(btn => {
        console.log("delete? ", btn.innerHTML, btn.innerHTML.indexOf("Delete"));
        if (btn.innerHTML.indexOf("Delete") !== -1) btn.click();
      });
      setTimeout(() => {
        document.querySelectorAll(".btn-primary").forEach(btn => {
          console.log("delete? ", btn.innerHTML, btn.innerHTML.indexOf("OK"));
          if (btn.innerHTML.indexOf("OK") !== -1) btn.click();
        });
        setTimeout(() => {
          var el = document.querySelector(".instance-id > span > a");
          if (el) processEl(el);
        }, timed);
      }, timed);
    }, timed);
  }, timed);
}

var el = document.querySelector(".instance-id > span > a");
processEl(el);

