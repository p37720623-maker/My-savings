<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <title>ตารางเก็บเงินของฉัน</title>
  <style>
    body { font-family: Tahoma, sans-serif; background: #f9f9f9; margin: 20px; }
    h2 { text-align: center; }
    table { border-collapse: collapse; width: 100%; margin-top: 20px; }
    th, td { border: 1px solid #ccc; padding: 6px 10px; text-align: center; }
    th { background: #eee; }
    .check { cursor: pointer; }
  </style>
</head>
<body>
  <h2>📅 ตารางเก็บเงิน ก.ย. 2568 – ม.ค. 2569</h2>
  <table>
    <tr>
      <th>เดือน</th>
      <th>จำนวนวันทำงาน</th>
      <th>เงินที่เก็บได้</th>
      <th>ยอดก่อนหัก</th>
      <th>หักค่าผ่อน</th>
      <th>ยอดคงเหลือ</th>
      <th>เช็ก ✔️</th>
    </tr>
    <tr>
      <td>ก.ย. 2568</td><td>17</td><td>680</td><td>680</td><td>-523</td><td>157</td>
      <td class="check" onclick="toggle(this)">⬜</td>
    </tr>
    <tr>
      <td>ต.ค. 2568</td><td>23</td><td>920</td><td>1077</td><td>-523</td><td>397</td>
      <td class="check" onclick="toggle(this)">⬜</td>
    </tr>
    <tr>
      <td>พ.ย. 2568</td><td>21</td><td>840</td><td>1237</td><td>-523</td><td>317</td>
      <td class="check" onclick="toggle(this)">⬜</td>
    </tr>
    <tr>
      <td>ธ.ค. 2568</td><td>22</td><td>880</td><td>1197</td><td>-523</td><td>357</td>
      <td class="check" onclick="toggle(this)">⬜</td>
    </tr>
    <tr>
      <td>ม.ค. 2569</td><td>0</td><td>0</td><td>357</td><td>-523</td><td>-166</td>
      <td class="check" onclick="toggle(this)">⬜</td>
    </tr>
  </table>

  <script>
    function toggle(cell) {
      cell.textContent = (cell.textContent === "⬜") ? "✔️" : "⬜";
      saveProgress();
    }
    function saveProgress() {
      let checks = [...document.querySelectorAll('.check')].map(c => c.textContent);
      localStorage.setItem("savingsChecks", JSON.stringify(checks));
    }
    function loadProgress() {
      let saved = JSON.parse(localStorage.getItem("savingsChecks") || "[]");
      let cells = document.querySelectorAll('.check');
      saved.forEach((val, i) => { if(cells[i]) cells[i].textContent = val; });
    }
    loadProgress();
  </script>
</body>
</html># My-savings
