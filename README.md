<html lang="id">
<head>
	<meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>tulz</title>
	<style>
		body {
			font-family: Arial, sans-serif;
			text-align: center;
			padding-top: 50px;
			background-color: #222;
			color: white;
			overflow-y: scroll;
		}
		.kotak-warna {
			width: 100px;
			height: 100px;
			margin: 10px;
			display: inline-block;
			cursor: pointer;
			border-radius: 8px;
		}
			
		h1, h3, h4, h5, h6 {
			font-size: 20px;
			text-align: left;
			padding: 5px;
		}
		button, input {
			padding: 10px;
			margin: 10px;
			font-size: 16px;
		}
		ul {
			font-family: Arial, sans-serif;
			text-align: left;
			padding: 10px;
			margin: 10px;
		}
		#hasil, #pesan{
			font-size: 20px;
			margin-top: 20px;
			font-weight: bold;
		}
		.ag {
			font-size: 30px;
			font-weight: bold;
			white-space: nowrap;
			animation: g 6s linear infinite, mh 2s linear infinite;
		}
		@keyframes g {
			0% {transform: translateX(100%); }
			100% {transform: translateX(-100%); }
		}
		@keyframes mh {
			0% {opacity: 0; }
			50% {opacity: 1; }
			100% {opacity: 0; }
		}
	</style>
	</head>
	<body>
		
        <h1>yo, perkenalkan aku adalah seorang anak yang bercita cita menjadi seorang trader sekaligus programer profesional</h1>
		
		<h1>tujuan ku membuat web ini agar aku mempunyai portofolio yang dapat aku lihat atau di pamerkan di masa depan</h1>
		
		<h1>aku juga mempunyai beberapa prinsip untuk terus bertahan dan konsisten, berikut prinsip-prinsip yang ku tetapkan</h1>
		
		<ul>
			<li>menyerah = pecundang</li>
			<li>konsisten = menang</li>
			<li>bertahan = kuat</li>
		</ul>
		  
		
		<h1>oh ya, selama aku belajar coding 1 bulan 13 hari, aku baru bisa membuat calculator dan itupun ga terlalu mencolok</h1>
		
		<h1>aku juga ingin memperlihatkan sedikit profile ku</h1>
    
    
    <ul>
    	<li>nama: fathul</li>
        <li>umur: 14</li>
        <li>introvert</li>
        <li>note: he will beat elon musk</li>
    </ul>
    
    
		<h1>oke mari fokus ke calculator nya</h1>
		<h1>berikut calculator yang dapat saya buat</h1>
		
		<h2>CALCULATOR</h2>
		
		<input type="number" id="angka1" placeholder="angka pertama">
		<input type="number" id="angka2" placeholder="angka kedua">
		
		<br><br>
		<button onclick="hitung('+')">+</button>
		<button onclick="hitung('-')">-</button>
		<button onclick="hitung('*')">*</button>
		<button onclick="hitung('/')">/</button>
		
		<p id="hasil">hasil: </p>
		
	<script>		
		let angkaBenar = Math.floor(Math.random() * 10) + 1;
		
		function hitung(operator) {
			let a = parseInt(document.getElementById("angka1").value);
			let b = parseInt(document.getElementById("angka2").value);	
			
		if (isNaN(a) || isNaN(b)) {
			hasil = "masukkan dua angka dulu";
		} else if (operator === '+') {
			hasil = a + b;
		} else if (operator === '-') {
			hasil = a - b;
		} else if (operator === '*') {
			hasil = a * b;
		} else if (operator === '/') {
			if (b === 0) hasil = "tak bisa dibagi 0";
			else hasil = a / b;
		}
		document.getElementById("hasil").innerText = "hasil: " + hasil;
		}
    </script>
    
    <h1>oh ya aku lupa memberi tahu bahwa aku juga bisa membuat game tebak angka! </h1>
    
    <h2>Guess The Number</h2>
    
    <input type="number" id="tebakan" placeholder="1-10">
    <button onclick="cekTebakan()">tebak</button>
    <button onclick="ulangGame()">ulang</button>
    
    <p id="percobaan">percobaan: 0</p>
    <p id="pesan">angka yang benar: </p>
    
    <script>
    	let angkaGame = Math.floor(Math.random() * 10) + 1;
        let percobaan = 0;
        
        function cekTebakan() {
        	let tebakan = parseFloat(document.getElementById("tebakan").value);
            let pesan = "";
            
            percobaan++;
   
            if (isNaN(tebakan)) {
        	pesan = "masukkan satu angka terlebih dahulu";
            } else if (tebakan > angkaGame) {
        	pesan = "kebesaran";            
            } else if (tebakan < angkaGame) {
        	pesan = "kekecilan";           
            } else  {
            pesan = "selamat, angka yang benar adalah: " + angkaGame;
            }
        
            document.getElementById("pesan").innerText = pesan;
            document.getElementById("percobaan").innerText = "percobaan: " + percobaan;
          }
        
        function ulangGame() {
        	angkaGame = Math.floor(Math.random() * 10) + 1;
            percobaan = 0;
            document.getElementById("pesan").innerText = "tebak angka baru";
            document.getElementById("percobaan").innerText = "percobaan: " + percobaan;
       }
    </script>
    
    <h1>oh iya masih ada yang bisa kubuat</h1>
    <h1>yang kubuat di projek ketiga ini adalah daftar tugas</h1>
    <h1>my td list</h1>
	<input type="text" id="taskInput" placeholder="masukkan daftar tugasmu">
	<button id="addBtn">tambah</button>
	
	<ul id="taskList"></ul>
	
	<script>
		let input = document.getElementById("taskInput");
		let addBtn = document.getElementById("addBtn");
		let taskList = document.getElementById("taskList");
		
		addBtn.addEventListener("click", function() {
			let task = input.value.trim();
			if (task === "") return;
			
			let li = document.createElement("li");
			li.textContent = task;
			
			let delBtn = document.createElement("button");
			delBtn.textContent = "hapus";
			
			delBtn.addEventListener("click", function() {
				li.remove();
			});
			
			li.appendChild(delBtn);
			taskList.appendChild(li);
			
			input.value = "";
		});
			
			
			
	</script>
	<h1>masih ada 1 yang bisa ku buat! </h1>
	
	<h2>TEBAK WARNA</h2>
	<p>warna yang harus ditebak: <span id="targetWarna"></span></p>
	<p id="pesanWarna"></p>
	<div id="kotakContainer"></div>
	<button onclick="ulangTebakWarna()">ulang</button>
	
	<script>
		let warna = ["red", "blue", "brown", "purple", "gray"];
		let warnaBenar = warna[Math.floor(Math.random() * warna.length)];
		
		function ulangTebakWarna() {
			warnaBenar = warna[Math.floor(Math.random() * warna.length)];
			document.getElementById("targetWarna").innerText = warnaBenar.toUpperCase();
			
			let container = document.getElementById("kotakContainer");
			container.innerHTML = "";
			
			warna.forEach(w => {
				let kotak = document.createElement("div");
				kotak.classList.add("kotak-warna");
				kotak.style.backgroundColor = w;
				kotak.onclick = function() {
					if (w === warnaBenar) {
						document.getElementById("pesanWarna").innerText = "benar";
					} else {
						document.getElementById("pesanWarna").innerText = "salah";
					}
				};
				container.appendChild(kotak);
			});
			
			document.getElementById("pesanWarna").innerText = "";
		}
		
		ulangTebakWarna();		
	</script>
    <h1 class="ag">terima kasih telah membaca sampai akhir</h1>
    <h1>sangat amat sederhana bukan?</h1>   
</body>
</html>
 		 
