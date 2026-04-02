<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>S-Aura | Elevated Lifestyle</title>
    <style>
        :root {
            --primary: #111111;
            --accent: #d4af37;
            --bg: #fafafa;
            --card-bg: #ffffff;
            --text: #222222;
            --muted: #777777;
        }
        
        * { box-sizing: border-box; }
        
        body {
            font-family: 'Segoe UI', -apple-system, BlinkMacSystemFont, Roboto, sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--bg);
            color: var(--text);
            line-height: 1.6;
        }
        
        header {
            background: var(--card-bg);
            padding: 30px 20px;
            text-align: center;
            border-bottom: 1px solid #eaeaea;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        header h1 {
            margin: 0;
            font-size: 2.2rem;
            color: var(--primary);
            letter-spacing: 4px;
            font-weight: 700;
        }
        
        header p {
            margin: 5px 0 0;
            color: var(--muted);
            font-size: 0.9rem;
            letter-spacing: 1px;
        }
        
        .container {
            max-width: 1200px;
            margin: 40px auto;
            padding: 0 20px;
        }
        
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background: var(--card-bg);
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 4px 20px rgba(0,0,0,0.03);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            display: flex;
            flex-direction: column;
            border: 1px solid #f0f0f0;
        }
        
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
        }
        
        .product-img {
            width: 100%;
            height: 280px;
            background: #f0f0f0;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--muted);
            font-size: 0.9rem;
            object-fit: cover;
        }
        
        .p-info {
            padding: 20px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }
        
        .p-title {
            font-size: 1.2rem;
            margin: 0 0 8px;
            font-weight: 600;
            color: var(--primary);
        }
        
        .p-desc {
            font-size: 0.85rem;
            color: var(--muted);
            margin-bottom: 15px;
            line-height: 1.5;
            flex-grow: 1;
        }
        
        .p-price {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 15px;
        }
        
        button {
            width: 100%;
            padding: 14px;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .buy-btn {
            background: var(--primary);
            color: white;
        }
        
        .buy-btn:hover {
            background: #333;
        }

        /* Modal Overlay */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.7);
            justify-content: center;
            align-items: center;
            z-index: 1000;
            padding: 20px;
        }
        
        .modal-content {
            background: white;
            padding: 30px;
            border-radius: 16px;
            width: 100%;
            max-width: 450px;
            position: relative;
            box-shadow: 0 15px 40px rgba(0,0,0,0.2);
            animation: slideUp 0.3s ease;
        }
        
        @keyframes slideUp {
            from { transform: translateY(20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        
        .close-btn {
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 1.8rem;
            cursor: pointer;
            color: var(--muted);
        }
        
        input {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 0.95rem;
        }
        
        input:focus {
            border-color: var(--accent);
            outline: none;
        }
        
        .bkash-box {
            background: #e2136e;
            color: white;
            padding: 16px;
            border-radius: 10px;
            text-align: center;
            margin: 15px 0;
            font-size: 0.95rem;
        }
        
        .submit-btn {
            background: #25D366; /* WhatsApp Green */
            color: white;
            margin-top: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .submit-btn:hover {
            background: #1ebd5c;
        }
    </style>
</head>
<body>

    <header>
        <h1>S-AURA</h1>
        <p>DROP SHOP INSPIRED MINIMALISM</p>
    </header>

    <div class="container">
        <div class="grid">
            
            <div class="product-card">
                <div class="product-img">AURA PREMIUM WATCH [IMAGE]</div>
                <div class="p-info">
                    <div class="p-title">Aura Classic Watch</div>
                    <div class="p-desc">Deep matte finish, minimal hands, and a premium vegan leather strap. Complete your stealth look.</div>
                    <div class="p-price">৳ 1,200</div>
                    <button class="buy-btn" onclick="openCheckout('Aura Classic Watch', '1200')">Buy Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-img">AURA LEATHER WALLET [IMAGE]</div>
                <div class="p-info">
                    <div class="p-title">S-Aura Minimal Wallet</div>
                    <div class="p-desc">Engineered for your front pocket. Aluminum and genuine top-grain leather with full RFID protection.</div>
                    <div class="p-price">৳ 750</div>
                    <button class="buy-btn" onclick="openCheckout('S-Aura Minimal Wallet', '750')">Buy Now</button>
                </div>
            </div>

            <div class="product-card">
                <div class="product-img">AURA PERFUME [IMAGE]</div>
                <div class="p-info">
                    <div class="p-title">Aura Signature Scent</div>
                    <div class="p-desc">A deep, long-lasting scent blending rich oud with modern amber notes. 50ml bottle.</div>
                    <div class="p-price">৳ 1,850</div>
                    <button class="buy-btn" onclick="openCheckout('Aura Signature Scent', '1850')">Buy Now</button>
                </div>
            </div>

        </div>
    </div>

    <div class="modal" id="checkoutModal">
        <div class="modal-content">
            <span class="close-btn" onclick="closeCheckout()">&times;</span>
            <h3 style="margin-top: 0; font-size: 1.4rem;">Secure Checkout</h3>
            <p id="orderSummary" style="font-weight: 600; margin-bottom: 20px;"></p>
            
            <form onsubmit="confirmOrder(event)">
                <input type="text" id="custName" placeholder="Full Name" required>
                <input type="text" id="custAddress" placeholder="Shipping Address" required>
                <input type="tel" id="custPhone" placeholder="Your Phone Number" required>
                
                <div class="bkash-box">
                    💳 <strong>Manual bKash Payment</strong><br>
                    Send Money to: <strong>01705665586</strong>
                </div>
                
                <input type="text" id="custTrx" placeholder="Enter Your bKash Transaction ID (TrxID)" required>
                
                <button type="submit" class="submit-btn">
                    💬 Submit Order via WhatsApp
                </button>
            </form>
        </div>
    </div>

    <script>
        let selectedProduct = "";
        let selectedPrice = "";

        // YOUR WHATSAPP NUMBER (with country code, no + sign)
        const ownerWhatsApp = "8801705665586"; 

        function openCheckout(name, price) {
            selectedProduct = name;
            selectedPrice = price;
            document.getElementById('orderSummary').innerText = "Product: " + name + " (৳ " + price + ")";
            document.getElementById('checkoutModal').style.display = 'flex';
        }

        function closeCheckout() {
            document.getElementById('checkoutModal').style.display = 'none';
        }

        function confirmOrder(e) {
            e.preventDefault();
            
            const name = document.getElementById('custName').value;
            const address = document.getElementById('custAddress').value;
            const phone = document.getElementById('custPhone').value;
            const trx = document.getElementById('custTrx').value;
            
            // Construct the WhatsApp message
            const message = `*NEW ORDER - S-AURA*%0A%0A` +
                            `*Product:* ${selectedProduct}%0A` +
                            `*Price:* ৳ ${selectedPrice}%0A%0A` +
                            `*Customer Name:* ${name}%0A` +
                            `*Address:* ${address}%0A` +
                            `*Phone:* ${phone}%0A` +
                            `*bKash TrxID:* ${trx}`;
            
            // Generate the full WhatsApp URL
            const waUrl = `https://wa.me/${ownerWhatsApp}?text=${message}`;
            
            // Redirect user to WhatsApp
            window.open(waUrl, '_blank');
            
            // Clear inputs and close
            e.target.reset();
            closeCheckout();
        }
        
        window.onclick = function(event) {
            let modal = document.getElementById('checkoutModal');
            if (event.target == modal) {
                closeCheckout();
            }
        }
    </script>
</body>
</html>
