<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>"TEMIRYO'LINFRATUZILMA" AJ 2024-2025 YIL HARAJATLARI</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
        }
        th, td {
            border: 1px solid #000;
            padding: 8px;
            text-align: center;
        }
        .total {
            font-weight: bold;
        }
        .increase {
            color: red; /* Oshgan bo'lsa, qizil rang */
        }
        .decrease {
            color: green; /* Kamaygan bo'lsa, yashil rang */
        }
    </style>
</head>
<body style="background-color: lightcyan;">

<h1>"TEMIRYO'LINFRATUZILMA" AJ 2024-2025 YIL HARAJATLARI</h1>

<label for="filial">Filialni tanlang:</label>
<select id="filial" onchange="updateUmumiyXarajatlar()">
    <option value="Toshkent">Toshkent MТU</option>
    <option value="Qo‘qon">Qo‘qon MТU</option>
    <option value="Buxoro">Buxoro MТU</option>
    <option value="Qung‘irot">Qung‘irot MТU</option>
    <option value="Qarshi">Qarshi MТU</option>
    <option value="Termiz">Termiz MТU</option>
    <option value="PDM">PDM BUHORO</option>
    <option value="ЦМД">ЦМД</option>
    <option value="УПП">УПП</option>
    <option value="МАРКАЗИЙ АППАРАТ">МАРКАЗИЙ АППАРАТ</option>
</select>

<label for="year">Yilni tanlang:</label>
<select id="year" onchange="updateUmumiyXarajatlar()">
    <option value="2024">2024 Yil</option>
    <option value="2025">2025 Yil</option>
</select>

<label for="chorak">Chorakni tanlang:</label>
<select id="chorak" onchange="updateUmumiyXarajatlar()">
    <option value="1">1-chorak</option>
    <option value="2">2-chorak</option>
    <option value="3">3-chorak</option>
    <option value="4">4-chorak</option>
</select>

<label for="oy">Oyni tanlang:</label>
<select id="oy" onchange="updateUmumiyXarajatlar()">
    <option value="1">Yanvar</option>
    <option value="2">Fevral</option>
    <option value="3">Mart</option>
    <option value="4">Aprel</option>
    <option value="5">May</option>
    <option value="6">Iyun</option>
    <option value="7">Iyul</option>
    <option value="8">Avgust</option>
    <option value="9">Sentabr</option>
    <option value="10">Oktyabr</option>
    <option value="11">Noyabr</option>
    <option value="12">Dekabr</option>
</select>

<h2>Xarajatlar</h2>
<table>
    <thead>
        <tr>
            <th>Xarajat Nomi</th>
            <th>Qiymat (ming so'm)</th>
            <th>Foiz (%)</th>
        </tr>
    </thead>
    <tbody id="xarajatlarTbody">
        <tr>
            <td>İSH HAQI</td>
            <td><input type="number" class="xarajat" data-nom="İSH HAQI" oninput="calculateTotal()"></td>
            <td><span class="foiz">0</span>%</td>
        </tr>
        <tr>
            <td>IJTIMOIY TULOV</td>
            <td><input type="number" class="xarajat" data-nom="IJTIMOIY TULOV" oninput="calculateTotal()"></td>
            <td><span class="foiz">0</span>%</td>
        </tr>
        <tr>
            <td>MATERIAL</td>
            <td><input type="number" class="xarajat" data-nom="MATERIAL" oninput="calculateTotal()"></td>
            <td><span class="foiz">0</span>%</td>
        </tr>
        <tr>
            <td>YOQILG'I</td>
            <td><input type="number" class="xarajat" data-nom="YOQILG'I" oninput="calculateTotal()"></td>
            <td><span class="foiz">0</span>%</td>
        </tr>
        <tr>
            <td>ELEKTR ENERGIYA</td>
            <td><input type="number" class="xarajat" data-nom="ELEKTR ENERGIYA" oninput="calculateTotal()"></td>
            <td><span class="foiz">0</span>%</td>
        </tr>
        <tr>
            <td>AMORTIZASIYA</td>
            <td><input type="number" class="xarajat" data-nom="AMORTIZASIYA" oninput="calculateTotal()"></td>
            <td><span class="foiz">0</span>%</td>
        </tr>
        <tr>
            <td>TA'MIRLASH FONDI</td>
            <td><input type="number" class="xarajat" data-nom="TA'MIRLASH FONDI" oninput="calculateTotal()"></td>
            <td><span class="foiz">0</span>%</td>
        </tr>
        <tr>
            <td>BOSHQA HARAJAT</td>
            <td><input type="number" class="xarajat" data-nom="BOSHQA HARAJAT" oninput="calculateTotal()"></td>
            <td><span class="foiz">0</span>%</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td class="total">Umumiy Xarajat</td>
            <td><span id="umumiyXarajat">0</span> ming so'm</td>
            <td><span id="umumiyFoiz">100</span>%</td>
        </tr>
    </tfoot>
</table>

<h2>Umumiy Xarajatlar</h2>
<table>
    <thead>
        <tr>
            <th>Xarajat Nomi</th>
            <th>Toshkent</th>
            <th>Qo‘qon</th>
            <th>Buxoro</th>
            <th>Qung‘irot</th>
            <th>Qarshi</th>
            <th>Termiz</th>
            <th>PDM</th>
            <th>ЦМД</th>
            <th>УПП</th>
            <th>МАРКАЗИЙ АППАРАТ</th>
            <th>JAMI</th>
        </tr>
    </thead>
    <tbody id="umumiyXarajatlarTbody"></tbody>
    <tfoot>
        <tr>
            <td class="total">Umumiy Xarajatlar</td>
            <td colspan="11" id="jamiXarajatlar">0</td>
        </tr>
    </tfoot>
</table>

<h2>O'tgan Oy Xarajatlari Taqqoslash</h2>
<table>
    <thead>
        <tr>
            <th>Xarajat Nomi</th>
            <th>O'tgan Oy</th>
            <th>Joriy Oy</th>
            <th>Farq (%)</th>
        </tr>
    </thead>
    <tbody id="taqqoslashTbody"></tbody>
</table>

<button onclick="confirmData()">Tasdiqlash</button>
<button onclick="resetData()">Ma'lumotlarni tozalash</button>

<script>
let totalXarajatlar = {
    "Toshkent": {},
    "Qo‘qon": {},
    "Buxoro": {},
    "Qung‘irot": {},
    "Qarshi": {},
    "Termiz": {},
    "PDM": {},
    "ЦМД": {},
    "УПП": {},
    "МАРКАЗИЙ АППАРАТ": {}
};

let eskiXarajatlar = {
    "Toshkent": {},
    "Qo‘qon": {},
    "Buxoro": {},
    "Qung‘irot": {},
    "Qarshi": {},
    "Termiz": {},
    "PDM": {},
    "ЦМД": {},
    "УПП": {},
    "МАРКАЗИЙ АППАРАТ": {}
};

function calculateTotal() {
    let total = 0;
    let xarajatlar = document.querySelectorAll(".xarajat");
    
    xarajatlar.forEach(function(input) {
        let qiymat = parseFloat(input.value) || 0;
        total += qiymat;
    });

    let umumiyXarajatElement = document.getElementById("umumiyXarajat");
    umumiyXarajatElement.textContent = total.toFixed(2);

    updatePercentages(total);
}

function updatePercentages(total) {
    let xarajatlar = document.querySelectorAll(".xarajat");
    let foizElements = document.querySelectorAll(".foiz");

    xarajatlar.forEach(function(inp22.10.2024 8:54:45ut, index) {
        let qiymat = parseFloat(input.value) || 0;
        let foiz = (qiymat / total) * 100 || 0;
        foizElements[index].textContent = foiz.toFixed(2);
    });

    document.getElementById("umumiyFoiz").textContent = "100";
}

function updateUmumiyXarajatlar() {
    let filial = document.getElementById("filial").value;
    let yil = document.getElementById("year").value;
    let chorak = document.getElementById("chorak").value;
    let oy = document.getElementById("oy").value;

    let xarajatInputs = document.querySelectorAll(".xarajat");

    xarajatInputs.forEach(function(input) {
        let nomi = input.getAttribute("data-nom");
        let qiymat = parseFloat(input.value) || 0;
        totalXarajatlar[filial][nomi] = qiymat;
    });

    updateUmumiyXarajatlarTbody();
}

function updateUmumiyXarajatlarTbody() {
    let tbody = document.getElementById("umumiyXarajatlarTbody");
    tbody.innerHTML = ""; // Tozalash

    let jamiXarajatlar = 0;

    for (let xarajatNomi in totalXarajatlar.Toshkent) {
        let row = document.createElement("tr");

        let nomiTd = document.createElement("td");
        nomiTd.textContent = xarajatNomi;
        row.appendChild(nomiTd);

        let jamiFilialXarajat = 0;

        for (let filial in totalXarajatlar) {
            let td = document.createElement("td");
            let qiymat = totalXarajatlar[filial][xarajatNomi] || 0;
            td.textContent = qiymat.toFixed(2);
            row.appendChild(td);
            jamiFilialXarajat += qiymat;
        }

        let jamiTd = document.createElement("td");
        jamiTd.textContent = jamiFilialXarajat.toFixed(2);
        row.appendChild(jamiTd);

        tbody.appendChild(row);

        jamiXarajatlar += jamiFilialXarajat;
    }

    document.getElementById("jamiXarajatlar").textContent = jamiXarajatlar.toFixed(2);
}

function confirmData() {
    let filial = document.getElementById("filial").value;
    eskiXarajatlar[filial] = JSON.parse(JSON.stringify(totalXarajatlar[filial]));

    updateTaqqoslashTbody();
}

function updateTaqqoslashTbody() {
    let tbody = document.getElementById("taqqoslashTbody");
    tbody.innerHTML = ""; // Tozalash

    let filial = document.getElementById("filial").value;

    for (let xarajatNomi in totalXarajatlar[filial]) {
        let row = document.createElement("tr");

        let nomiTd = document.createElement("td");
        nomiTd.textContent = xarajatNomi;
        row.appendChild(nomiTd);

        let eskiQiymat = eskiXarajatlar[filial][xarajatNomi] || 0;
        let yangiQiymat = totalXarajatlar[filial][xarajatNomi] || 0;

        let eskiTd = document.createElement("td");
        eskiTd.textContent = eskiQiymat.toFixed(2);
        row.appendChild(eskiTd);

        let yangiTd = document.createElement("td");
        yangiTd.textContent = yangiQiymat.toFixed(2);
        row.appendChild(yangiTd);

        let farqTd = document.createElement("td");
        let farq = ((yangiQiymat - eskiQiymat) / eskiQiymat) * 100 || 0;
        farqTd.textContent = farq.toFixed(2) + "%";
        farqTd.className = farq > 0 ? "increase" : "decrease";
        row.appendChild(farqTd);

        tbody.appendChild(row);
    }
}

function resetData() {
    document.querySelectorAll(".xarajat").forEach(input => {
        input.value = "";
    });
    calculateTotal();
    updateUmumiyXarajatlarTbody();
}
</script>

</body>
</html>
