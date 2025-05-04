# BenzariyManagemen
<!DOCTYPE html>
<html lang="ku" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>سیستەمی بەڕێوەبردنی بەرهەمەکانی مزگەوتی بنزێریان</title>
    <style>
        @font-face {
            font-family: 'NRT';
            src: url('assets/Nastaliq.ttf') format('truetype');
        }
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        body {
            font-family: 'NRT', Arial, sans-serif;
            background: linear-gradient(135deg, #e0f7fa, #e3f2fd);
            padding: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow-x: hidden;
        }
        .container {
            width: 100%;
            max-width: 900px;
            background: #ffffff;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            border: 1px solid #e0e7ff;
            position: relative;
            overflow: hidden;
        }
        .header {
            background: linear-gradient(45deg, #0288d1, #4fc3f7);
            padding: 15px;
            border-radius: 8px 8px 0 0;
            margin: -20px -20px 20px;
            text-align: center;
            color: #fff;
            font-size: 22px;
            font-weight: bold;
            text-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
        }
        .form-group {
            margin-bottom: 15px;
            position: relative;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #01579b;
            font-size: 14px;
        }
        input, select {
            width: 100%;
            padding: 8px;
            border: 1px solid #b3e5fc;
            border-radius: 6px;
            font-family: 'NRT', Arial, sans-serif;
            font-size: 13px;
            background: #e1f5fe;
            transition: all 0.3s ease;
        }
        input:focus, select:focus {
            border-color: #0288d1;
            box-shadow: 0 0 5px rgba(2, 136, 209, 0.3);
            background: #fff;
            outline: none;
        }
        input[type="file"] {
            padding: 5px;
        }
        .product-image, .report-image {
            width: 50px;
            height: 50px;
            object-fit: cover;
            border-radius: 4px;
        }
        button {
            background: linear-gradient(45deg, #0288d1, #4fc3f7);
            color: white;
            padding: 10px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-family: 'NRT', Arial, sans-serif;
            font-size: 14px;
            transition: all 0.3s ease;
            box-shadow: 0 2px 10px rgba(2, 136, 209, 0.3);
            width: 100%;
            margin: 5px 0;
        }
        button:hover {
            background: linear-gradient(45deg, #0277bd, #42a5f5);
            box-shadow: 0 4px 12px rgba(2, 136, 209, 0.5);
        }
        .delete-btn {
            background: linear-gradient(45deg, #d81b60, #f06292);
            box-shadow: 0 2px 10px rgba(216, 27, 96, 0.3);
        }
        .delete-btn:hover {
            background: linear-gradient(45deg, #c2185b, #ec407a);
            box-shadow: 0 4px 12px rgba(216, 27, 96, 0.5);
        }
        .edit-btn {
            background: linear-gradient(45deg, #2e7d32, #66bb6a);
            box-shadow: 0 2px 10px rgba(46, 125, 50, 0.3);
        }
        .edit-btn:hover {
            background: linear-gradient(45deg, #1b5e20, #4caf50);
            box-shadow: 0 4px 12px rgba(46, 125, 50, 0.5);
        }
        table {
            width: 100%;
            border-collapse: separate;
            border-spacing: 0;
            margin-top: 20px;
            background: #fff;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 3px 15px rgba(0, 0, 0, 0.1);
            display: block;
            overflow-x: auto;
            white-space: nowrap;
        }
        th, td {
            padding: 10px;
            text-align: center;
            border-bottom: 1px solid #e0e7ff;
            font-size: 13px;
        }
        th {
            background: linear-gradient(45deg, #0288d1, #4fc3f7);
            color: white;
            font-weight: bold;
            font-size: 13px;
        }
        tr:last-child td {
            border-bottom: none;
        }
        tr:hover {
            background: #e1f5fe;
            transition: background 0.3s;
        }
        .filter-section {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 20px;
            background: #e3f2fd;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
        }

        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }
            .header {
                font-size: 20px;
                padding: 12px;
                margin: -15px -15px 15px;
            }
            .form-group {
                margin-bottom: 12px;
            }
            label {
                font-size: 13px;
            }
            input, select {
                padding: 7px;
                font-size: 12px;
            }
            button {
                padding: 8px;
                font-size: 13px;
            }
            .filter-section {
                flex-direction: column;
                gap: 10px;
            }
        }
        @media (max-width: 480px) {
            .container {
                padding: 10px;
            }
            .header {
                font-size: 18px;
                padding: 10px;
            }
            label {
                font-size: 12px;
            }
            input, select {
                padding: 6px;
                font-size: 11px;
            }
            button {
                padding: 6px;
                font-size: 12px;
            }
            th, td {
                padding: 8px;
                font-size: 11px;
            }
            .edit-btn, .delete-btn {
                padding: 5px 8px;
                font-size: 10px;
            }
            .filter-section {
                padding: 10px;
            }
            .product-image, .report-image {
                width: 40px;
                height: 40px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">سیستەمی بەڕێوەبردنی بەرهەمەکانی مزگەوتی بنزێریان</div>

        <!-- Filter Section -->
        <div class="filter-section">
            <div class="form-group">
                <label>فلتەرکردن بە جۆر</label>
                <select id="filterType" onchange="filterProducts()">
                    <option value="all">هەموو</option>
                    <option value="پارچە">پارچە</option>
                    <option value="کیلۆ">کیلۆ</option>
                    <option value="دانە">دانە</option>
                    <option value="کارتۆن">کارتۆن</option>
                </select>
            </div>
            <div class="form-group">
                <label>فلتەرکردن بە ناو</label>
                <input type="text" id="filterName" placeholder="ناوی بەرهەم بگەڕێ" oninput="filterProducts()">
            </div>
        </div>

        <!-- Product Form -->
        <div class="form-group">
            <label>ناوی بەرهەم</label>
            <input type="text" id="productName" placeholder="ناوی بەرهەم">
        </div>
        <div class="form-group">
            <label>جۆری بەرهەم</label>
            <select id="productType">
                <option value="پارچە">پارچە</option>
                <option value="کیلۆ">کیلۆ</option>
                <option value="دانە">دانە</option>
                <option value="کارتۆن">کارتۆن</option>
            </select>
        </div>
        <div class="form-group">
            <label>بڕ</label>
            <input type="number" id="quantity" placeholder="بڕی بەرهەم">
        </div>
        <div class="form-group">
            <label>نرخ (بە دینار)</label>
            <input type="number" id="price" placeholder="نرخی بەرهەم">
        </div>
        <div class="form-group">
            <label>وێنەی بەرهەم</label>
            <input type="file" id="productImage" accept="image/*">
        </div>
        <div class="form-group">
            <label>وێنەی ڕاپۆرت</label>
            <input type="file" id="reportImage" accept="image/*">
        </div>
        <div class="form-group">
            <label>تێبینی</label>
            <input type="text" id="note" placeholder="تێبینی دەربارەی بەرهەم">
        </div>
        <button onclick="addOrUpdateProduct()">زۆرکردن یان نوێکردنەوە</button>
        <button onclick="generateReport()">دروستکردنی ڕاپۆرت</button>

        <!-- Product Table -->
        <table id="productTable">
            <thead>
                <tr>
                    <th>ناوی بەرهەم</th>
                    <th>جۆر</th>
                    <th>بڕ</th>
                    <th>نرخ</th>
                    <th>وێنەی بەرهەم</th>
                    <th>وێنەی ڕاپۆرت</th>
                    <th>تێبینی</th>
                    <th>بەروار</th>
                    <th>کردار</th>
                </tr>
            </thead>
            <tbody id="productBody"></tbody>
        </table>
    </div>

    <canvas id="reportCanvas"></canvas>

    <script src="assets/html2canvas.min.js"></script>
    <script>
        let products = JSON.parse(localStorage.getItem('products')) || [];
        let editingProductId = null;

        function saveProducts() {
            localStorage.setItem('products', JSON.stringify(products));
        }

        function addOrUpdateProduct() {
            const productName = document.getElementById('productName').value;
            const productType = document.getElementById('productType').value;
            const quantity = document.getElementById('quantity').value;
            const price = document.getElementById('price').value;
            const note = document.getElementById('note').value;
            const productImageInput = document.getElementById('productImage');
            const reportImageInput = document.getElementById('reportImage');
            let productImageData = '';
            let reportImageData = '';

            if (!productName || !quantity || !price) {
                alert('تکایە ناوی بەرهەم، بڕ، و نرخ پڕ بکەرەوە');
                return;
            }

            if (productImageInput.files && productImageInput.files[0]) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    productImageData = e.target.result;
                    handleReportImage();
                };
                reader.readAsDataURL(productImageInput.files[0]);
            } else {
                handleReportImage();
            }

            function handleReportImage() {
                if (reportImageInput.files && reportImageInput.files[0]) {
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        reportImageData = e.target.result;
                        saveProduct();
                    };
                    reader.readAsDataURL(reportImageInput.files[0]);
                } else {
                    saveProduct();
                }
            }

            function saveProduct() {
                const product = {
                    id: editingProductId || Date.now(),
                    productName,
                    productType,
                    quantity: parseFloat(quantity),
                    price: parseFloat(price),
                    image: productImageData,
                    reportImage: reportImageData,
                    note,
                    date: new Date().toLocaleDateString('ku-IQ')
                };

                if (editingProductId) {
                    products = products.map(p => p.id === editingProductId ? product : p);
                    editingProductId = null;
                } else {
                    products.push(product);
                }

                saveProducts();
                filterProducts();
                clearInputs();
            }
        }

        function clearInputs() {
            document.getElementById('productName').value = '';
            document.getElementById('quantity').value = '';
            document.getElementById('price').value = '';
            document.getElementById('note').value = '';
            document.getElementById('productImage').value = '';
            document.getElementById('reportImage').value = '';
            document.getElementById('productType').value = 'پارچە';
        }

        function renderProducts(filteredProducts) {
            const productBody = document.getElementById('productBody');
            productBody.innerHTML = '';

            filteredProducts.forEach(product => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${product.productName}</td>
                    <td>${product.productType}</td>
                    <td>${product.quantity}</td>
                    <td>${product.price}</td>
                    <td>${product.image ? `<img src="${product.image}" class="product-image" alt="وێنەی بەرهەم">` : 'بەتاڵ'}</td>
                    <td>${product.reportImage ? `<img src="${product.reportImage}" class="report-image" alt="وێنەی ڕاپۆرت">` : 'بەتاڵ'}</td>
                    <td>${product.note}</td>
                    <td>${product.date}</td>
                    <td>
                        <button class="edit-btn" onclick="editProduct(${product.id})">دەستکاری</button>
                        <button class="delete-btn" onclick="deleteProduct(${product.id})">سڕینەوە</button>
                    </td>
                `;
                productBody.appendChild(row);
            });
        }

        function editProduct(id) {
            const product = products.find(p => p.id === id);
            if (product) {
                document.getElementById('productName').value = product.productName;
                document.getElementById('productType').value = product.productType;
                document.getElementById('quantity').value = product.quantity;
                document.getElementById('price').value = product.price;
                document.getElementById('note').value = product.note;
                editingProductId = id;
            }
        }

        function deleteProduct(id) {
            products = products.filter(product => product.id !== id);
            saveProducts();
            filterProducts();
        }

        function filterProducts() {
            const filterType = document.getElementById('filterType').value;
            const filterName = document.getElementById('filterName').value.toLowerCase();

            let filteredProducts = products;

            if (filterType !== 'all') {
                filteredProducts = filteredProducts.filter(product => product.productType === filterType);
            }

            if (filterName) {
                filteredProducts = filteredProducts.filter(product => 
                    product.productName.toLowerCase().includes(filterName)
                );
            }

            renderProducts(filteredProducts);
        }

        function generateReport() {
            const container = document.querySelector('.container');
            html2canvas(container).then(canvas => {
                const link = document.createElement('a');
                link.download = 'مزگەوتی_بنزێریان_ڕاپۆرتی_بەرهەمەکان.png';
                link.href = canvas.toDataURL();
                link.click();
            });
        }

        filterProducts();
    </script>
</body>
</html><!DOCTYPE html>
<html lang="ku" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>سیستەمی بەڕێوەبردنی بەرهەمەکانی مزگەوتی بنزێریان</title>
    <style>
        @font-face {
            font-family: 'NRT';
            src: url('assets/Nastaliq.ttf') format('truetype');
        }
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        body {
            font-family: 'NRT', Arial, sans-serif;
            background: linear-gradient(135deg, #e0f7fa, #e3f2fd);
            padding: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow-x: hidden;
        }
        .container {
            width: 100%;
            max-width: 900px;
            background: #ffffff;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            border: 1px solid #e0e7ff;
            position: relative;
            overflow: hidden;
        }
        .header {
            background: linear-gradient(45deg, #0288d1, #4fc3f7);
            padding: 15px;
            border-radius: 8px 8px 0 0;
            margin: -20px -20px 20px;
            text-align: center;
            color: #fff;
            font-size: 22px;
            font-weight: bold;
            text-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
        }
        .form-group {
            margin-bottom: 15px;
            position: relative;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #01579b;
            font-size: 14px;
        }
        input, select {
            width: 100%;
            padding: 8px;
            border: 1px solid #b3e5fc;
            border-radius: 6px;
            font-family: 'NRT', Arial, sans-serif;
            font-size: 13px;
            background: #e1f5fe;
            transition: all 0.3s ease;
        }
        input:focus, select:focus {
            border-color: #0288d1;
            box-shadow: 0 0 5px rgba(2, 136, 209, 0.3);
            background: #fff;
            outline: none;
        }
        input[type="file"] {
            padding: 5px;
        }
        .product-image, .report-image {
            width: 50px;
            height: 50px;
            object-fit: cover;
            border-radius: 4px;
        }
        button {
            background: linear-gradient(45deg, #0288d1, #4fc3f7);
            color: white;
            padding: 10px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-family: 'NRT', Arial, sans-serif;
            font-size: 14px;
            transition: all 0.3s ease;
            box-shadow: 0 2px 10px rgba(2, 136, 209, 0.3);
            width: 100%;
            margin: 5px 0;
        }
        button:hover {
            background: linear-gradient(45deg, #0277bd, #42a5f5);
            box-shadow: 0 4px 12px rgba(2, 136, 209, 0.5);
        }
        .delete-btn {
            background: linear-gradient(45deg, #d81b60, #f06292);
            box-shadow: 0 2px 10px rgba(216, 27, 96, 0.3);
        }
        .delete-btn:hover {
            background: linear-gradient(45deg, #c2185b, #ec407a);
            box-shadow: 0 4px 12px rgba(216, 27, 96, 0.5);
        }
        .edit-btn {
            background: linear-gradient(45deg, #2e7d32, #66bb6a);
            box-shadow: 0 2px 10px rgba(46, 125, 50, 0.3);
        }
        .edit-btn:hover {
            background: linear-gradient(45deg, #1b5e20, #4caf50);
            box-shadow: 0 4px 12px rgba(46, 125, 50, 0.5);
        }
        table {
            width: 100%;
            border-collapse: separate;
            border-spacing: 0;
            margin-top: 20px;
            background: #fff;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 3px 15px rgba(0, 0, 0, 0.1);
            display: block;
            overflow-x: auto;
            white-space: nowrap;
        }
        th, td {
            padding: 10px;
            text-align: center;
            border-bottom: 1px solid #e0e7ff;
            font-size: 13px;
        }
        th {
            background: linear-gradient(45deg, #0288d1, #4fc3f7);
            color: white;
            font-weight: bold;
            font-size: 13px;
        }
        tr:last-child td {
            border-bottom: none;
        }
        tr:hover {
            background: #e1f5fe;
            transition: background 0.3s;
        }
        .filter-section {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 20px;
            background: #e3f2fd;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
        }

        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }
            .header {
                font-size: 20px;
                padding: 12px;
                margin: -15px -15px 15px;
            }
            .form-group {
                margin-bottom: 12px;
            }
            label {
                font-size: 13px;
            }
            input, select {
                padding: 7px;
                font-size: 12px;
            }
            button {
                padding: 8px;
                font-size: 13px;
            }
            .filter-section {
                flex-direction: column;
                gap: 10px;
            }
        }
        @media (max-width: 480px) {
            .container {
                padding: 10px;
            }
            .header {
                font-size: 18px;
                padding: 10px;
            }
            label {
                font-size: 12px;
            }
            input, select {
                padding: 6px;
                font-size: 11px;
            }
            button {
                padding: 6px;
                font-size: 12px;
            }
            th, td {
                padding: 8px;
                font-size: 11px;
            }
            .edit-btn, .delete-btn {
                padding: 5px 8px;
                font-size: 10px;
            }
            .filter-section {
                padding: 10px;
            }
            .product-image, .report-image {
                width: 40px;
                height: 40px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">سیستەمی بەڕێوەبردنی بەرهەمەکانی مزگەوتی بنزێریان</div>

        <!-- Filter Section -->
        <div class="filter-section">
            <div class="form-group">
                <label>فلتەرکردن بە جۆر</label>
                <select id="filterType" onchange="filterProducts()">
                    <option value="all">هەموو</option>
                    <option value="پارچە">پارچە</option>
                    <option value="کیلۆ">کیلۆ</option>
                    <option value="دانە">دانە</option>
                    <option value="کارتۆن">کارتۆن</option>
                </select>
            </div>
            <div class="form-group">
                <label>فلتەرکردن بە ناو</label>
                <input type="text" id="filterName" placeholder="ناوی بەرهەم بگەڕێ" oninput="filterProducts()">
            </div>
        </div>

        <!-- Product Form -->
        <div class="form-group">
            <label>ناوی بەرهەم</label>
            <input type="text" id="productName" placeholder="ناوی بەرهەم">
        </div>
        <div class="form-group">
            <label>جۆری بەرهەم</label>
            <select id="productType">
                <option value="پارچە">پارچە</option>
                <option value="کیلۆ">کیلۆ</option>
                <option value="دانە">دانە</option>
                <option value="کارتۆن">کارتۆن</option>
            </select>
        </div>
        <div class="form-group">
            <label>بڕ</label>
            <input type="number" id="quantity" placeholder="بڕی بەرهەم">
        </div>
        <div class="form-group">
            <label>نرخ (بە دینار)</label>
            <input type="number" id="price" placeholder="نرخی بەرهەم">
        </div>
        <div class="form-group">
            <label>وێنەی بەرهەم</label>
            <input type="file" id="productImage" accept="image/*">
        </div>
        <div class="form-group">
            <label>وێنەی ڕاپۆرت</label>
            <input type="file" id="reportImage" accept="image/*">
        </div>
        <div class="form-group">
            <label>تێبینی</label>
            <input type="text" id="note" placeholder="تێبینی دەربارەی بەرهەم">
        </div>
        <button onclick="addOrUpdateProduct()">زۆرکردن یان نوێکردنەوە</button>
        <button onclick="generateReport()">دروستکردنی ڕاپۆرت</button>

        <!-- Product Table -->
        <table id="productTable">
            <thead>
                <tr>
                    <th>ناوی بەرهەم</th>
                    <th>جۆر</th>
                    <th>بڕ</th>
                    <th>نرخ</th>
                    <th>وێنەی بەرهەم</th>
                    <th>وێنەی ڕاپۆرت</th>
                    <th>تێبینی</th>
                    <th>بەروار</th>
                    <th>کردار</th>
                </tr>
            </thead>
            <tbody id="productBody"></tbody>
        </table>
    </div>

    <canvas id="reportCanvas"></canvas>

    <script src="assets/html2canvas.min.js"></script>
    <script>
        let products = JSON.parse(localStorage.getItem('products')) || [];
        let editingProductId = null;

        function saveProducts() {
            localStorage.setItem('products', JSON.stringify(products));
        }

        function addOrUpdateProduct() {
            const productName = document.getElementById('productName').value;
            const productType = document.getElementById('productType').value;
            const quantity = document.getElementById('quantity').value;
            const price = document.getElementById('price').value;
            const note = document.getElementById('note').value;
            const productImageInput = document.getElementById('productImage');
            const reportImageInput = document.getElementById('reportImage');
            let productImageData = '';
            let reportImageData = '';

            if (!productName || !quantity || !price) {
                alert('تکایە ناوی بەرهەم، بڕ، و نرخ پڕ بکەرەوە');
                return;
            }

            if (productImageInput.files && productImageInput.files[0]) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    productImageData = e.target.result;
                    handleReportImage();
                };
                reader.readAsDataURL(productImageInput.files[0]);
            } else {
                handleReportImage();
            }

            function handleReportImage() {
                if (reportImageInput.files && reportImageInput.files[0]) {
                    const reader = new FileReader();
                    reader.onload = function(e) {
                        reportImageData = e.target.result;
                        saveProduct();
                    };
                    reader.readAsDataURL(reportImageInput.files[0]);
                } else {
                    saveProduct();
                }
            }

            function saveProduct() {
                const product = {
                    id: editingProductId || Date.now(),
                    productName,
                    productType,
                    quantity: parseFloat(quantity),
                    price: parseFloat(price),
                    image: productImageData,
                    reportImage: reportImageData,
                    note,
                    date: new Date().toLocaleDateString('ku-IQ')
                };

                if (editingProductId) {
                    products = products.map(p => p.id === editingProductId ? product : p);
                    editingProductId = null;
                } else {
                    products.push(product);
                }

                saveProducts();
                filterProducts();
                clearInputs();
            }
        }

        function clearInputs() {
            document.getElementById('productName').value = '';
            document.getElementById('quantity').value = '';
            document.getElementById('price').value = '';
            document.getElementById('note').value = '';
            document.getElementById('productImage').value = '';
            document.getElementById('reportImage').value = '';
            document.getElementById('productType').value = 'پارچە';
        }

        function renderProducts(filteredProducts) {
            const productBody = document.getElementById('productBody');
            productBody.innerHTML = '';

            filteredProducts.forEach(product => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${product.productName}</td>
                    <td>${product.productType}</td>
                    <td>${product.quantity}</td>
                    <td>${product.price}</td>
                    <td>${product.image ? `<img src="${product.image}" class="product-image" alt="وێنەی بەرهەم">` : 'بەتاڵ'}</td>
                    <td>${product.reportImage ? `<img src="${product.reportImage}" class="report-image" alt="وێنەی ڕاپۆرت">` : 'بەتاڵ'}</td>
                    <td>${product.note}</td>
                    <td>${product.date}</td>
                    <td>
                        <button class="edit-btn" onclick="editProduct(${product.id})">دەستکاری</button>
                        <button class="delete-btn" onclick="deleteProduct(${product.id})">سڕینەوە</button>
                    </td>
                `;
                productBody.appendChild(row);
            });
        }

        function editProduct(id) {
            const product = products.find(p => p.id === id);
            if (product) {
                document.getElementById('productName').value = product.productName;
                document.getElementById('productType').value = product.productType;
                document.getElementById('quantity').value = product.quantity;
                document.getElementById('price').value = product.price;
                document.getElementById('note').value = product.note;
                editingProductId = id;
            }
        }

        function deleteProduct(id) {
            products = products.filter(product => product.id !== id);
            saveProducts();
            filterProducts();
        }

        function filterProducts() {
            const filterType = document.getElementById('filterType').value;
            const filterName = document.getElementById('filterName').value.toLowerCase();

            let filteredProducts = products;

            if (filterType !== 'all') {
                filteredProducts = filteredProducts.filter(product => product.productType === filterType);
            }

            if (filterName) {
                filteredProducts = filteredProducts.filter(product => 
                    product.productName.toLowerCase().includes(filterName)
                );
            }

            renderProducts(filteredProducts);
        }

        function generateReport() {
            const container = document.querySelector('.container');
            html2canvas(container).then(canvas => {
                const link = document.createElement('a');
                link.download = 'مزگەوتی_بنزێریان_ڕاپۆرتی_بەرهەمەکان.png';
                link.href = canvas.toDataURL();
                link.click();
            });
        }

        filterProducts();
    </script>
</body>
</html>
