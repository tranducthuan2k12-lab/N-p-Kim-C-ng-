<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FF TOPUP</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,sans-serif;
}

body{
    background:#111;
    color:white;
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
}

.container{
    width:90%;
    max-width:400px;
    background:#1c1c1c;
    padding:25px;
    border-radius:15px;
    box-shadow:0 0 20px rgba(255,140,0,.3);
}

.logo{
    text-align:center;
    font-size:28px;
    font-weight:bold;
    color:#ff9800;
    margin-bottom:20px;
}

.title{
    text-align:center;
    margin-bottom:20px;
}

input,select{
    width:100%;
    padding:12px;
    margin:10px 0;
    border:none;
    border-radius:8px;
    background:#2a2a2a;
    color:white;
}

button{
    width:100%;
    padding:13px;
    border:none;
    border-radius:8px;
    background:#ff9800;
    color:white;
    font-size:16px;
    cursor:pointer;
    margin-top:10px;
}

button:hover{
    opacity:.9;
}

#popup{
    display:none;
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.7);
    justify-content:center;
    align-items:center;
}

.popup-box{
    background:white;
    color:black;
    padding:20px;
    border-radius:12px;
    text-align:center;
    width:300px;
}

.popup-box button{
    margin-top:15px;
}
</style>
</head>

<body>

<div class="container">
    <div class="logo">FF TOPUP</div>

    <div class="title">
        Nạp Kim Cương Free Fire
    </div>

    <input type="text" id="uid" placeholder="Nhập UID Game">

    <select id="kc">
        <option value="">Chọn gói Kim Cương</option>
        <option>110 Kim Cương</option>
        <option>220 Kim Cương</option>
        <option>530 Kim Cương</option>
        <option>1060 Kim Cương</option>
        <option>2180 Kim Cương</option>
    </select>

    <button onclick="napNgay()">Nạp Ngay</button>
</div>

<div id="popup">
    <div class="popup-box">
        <h2>✅ Thành Công</h2>
        <p id="thongbao"></p>
        <button onclick="dongPopup()">Đóng</button>
    </div>
</div>

<script>
function napNgay(){
    let uid = document.getElementById("uid").value;
    let kc = document.getElementById("kc").value;

    if(uid === ""){
        alert("Vui lòng nhập UID!");
        return;
    }

    if(kc === ""){
        alert("Vui lòng chọn gói Kim Cương!");
        return;
    }

    document.getElementById("thongbao").innerHTML =
        "Nạp thành công " + kc + " cho UID " + uid;

    document.getElementById("popup").style.display = "flex";
}

function dongPopup(){
    document.getElementById("popup").style.display = "none";
}
</script>

</body>
</html>
