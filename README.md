### Hi there 👋

<!--
**Daniel9D/Daniel9D** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

<div>
  <a href="https://github.com/daniel9d">
  <img height="150em" src="https://github-readme-stats.vercel.app/api?username=daniel9d&show_icons=true&theme=codeSTACKr&include_all_commits=true&count_private=true"/>
  <img height="auto" src="https://github-readme-stats.vercel.app/api/top-langs/?username=daniel9d&hide=html&layout=compact=true&theme=codeSTACKr"/>
</div>


<div>
<style>
    body {
      background: #0d1117;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .grid {
      display: grid;
      grid-template-columns: repeat(53, 12px);
      grid-template-rows: repeat(7, 12px);
      gap: 4px;
    }
    .cell {
      width: 10px;
      height: 10px;
      background-color: #161b22;
      border-radius: 2px;
      transition: background-color 0.3s;
    }
    .cell.active {
      background-color: #26a641;
    }
  </style>
  <div class="grid" id="grid"></div>

  <script>
  const grid = document.getElementById('grid');
  const cols = 53;
  const rows = 7;
  const cells = [];

  for (let r = 0; r < rows; r++) {
    const row = [];
    for (let c = 0; c < cols; c++) {
      const cell = document.createElement('div');
      cell.className = 'cell';
      grid.appendChild(cell);
      row.push(cell);
    }
    cells.push(row);
  }

  function animate() {
    const time = Date.now() * 0.002;

    for (let c = 0; c < cols; c++) {
      const height = Math.floor((Math.sin(time + c * 0.5) + 1) * (rows / 2));
      for (let r = 0; r < rows; r++) {
        const cell = cells[rows - r - 1][c]; // inverter para começar de baixo
        if (r < height) {
          cell.classList.add('active');
        } else {
          cell.classList.remove('active');
        }
      }
    }

    requestAnimationFrame(animate);
  }

  animate();
</script>
</div>
