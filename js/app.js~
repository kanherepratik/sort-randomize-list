(() => {
  const populateTable = userData => {
    const tbody = document.getElementById("table-content");
    tbody.innerHTML = "";
    userData.forEach(item => {
      const tableRow = document.createElement("tr");
      Object.keys(item).forEach(key => {
        const tableData = document.createElement("td");
        if (key === "thumbnailUrl") {
          const imgTag = document.createElement("img");
          imgTag.setAttribute("src", item[key]);
          tableData.appendChild(imgTag);
        } else {
          tableData.appendChild(document.createTextNode(item[key]));
        }
        tableRow.appendChild(tableData);
      });
      tbody.appendChild(tableRow);
    });
  };

  populateTable(TABLE_DATA);

  const sortBtn = document.getElementById("sort");
  sortBtn.onclick = function() {
    console.log(TABLE_DATA.sort().reverse());
    populateTable(TABLE_DATA.sort((a, b) => (a.price > b.price ? -1 : 1)));
  };

  function shuffle(array) {
    return array.sort(() => Math.random() - 0.5);
  }

  const startBtn = document.getElementById("start");
  startBtn.onclick = function() {
    const stopBtn = document.getElementById("stop");
    stopBtn.onclick = function() {
      clearInterval(timeOut);
    };
    alert("1 sec done");
    var timeOut = setInterval(() => populateTable(shuffle(TABLE_DATA)), 1000);
  };
})(); // end of file
