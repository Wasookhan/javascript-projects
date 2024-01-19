#solution code

```javascript

const input = document.querySelector("#input");
const addTask = document.querySelector("#addTask");
let listContainer = document.querySelector(".list-container");

addTask.addEventListener("click", () => {
  if (input.value === "") {
    alert("Please enter a task");
  } else {
    let li = document.createElement("li");
    li.innerHTML = input.value;
    listContainer.appendChild(li);
    input.value = "";
    saveData();
    let deleteBtn = document.createElement("button");
    deleteBtn.textContent = "Delete";
    deleteBtn.classList.add("Delete");
    li.appendChild(deleteBtn);
    deleteBtn.addEventListener("click", () => {
      li.remove();
      showData();
    });
  }
});
function saveData() {
  localStorage.setItem("data", listContainer.innerHTML);
}
function showData() {
  localStorage.getItem("data");
}

```