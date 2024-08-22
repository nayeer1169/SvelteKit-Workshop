<script lang="ts">
    import { PrivateKey } from '@bsv/sdk';
    
    let WIF: string = "Not generated yet";
    let address: string = "Not generated yet";
    
    function createKeys() {
        const privKey = PrivateKey.fromRandom();
        WIF = privKey.toWif();
        console.log("Private Key WIF format is ", WIF);
        address = privKey.toAddress();
        console.log("Your Bitcoin address is ", address);
    }
</script>

<style>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 20px;
        background-color: #f9f9f9;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        margin-top: 20px;
    }

    .button {
        background-color: #000;
        color: #fff;
        padding: 10px 20px;
        border-radius: 5px;
        margin-top: 20px;
        cursor: pointer;
        transition: background-color 0.3s;
    }

    .button:hover {
        background-color: #444;
    }

    .keys {
        margin-top: 20px;
        text-align: center;
    }

    .key {
        margin: 10px 0;
        padding: 10px;
        background-color: #eaeaea;
        border-radius: 5px;
        font-family: monospace;
        word-break: break-all;
    }

    .variable {
        color: #bbcf00;
        font-weight: bold;
    }
</style>

<section class="container">
    <button class="button" on:click={createKeys}>Generate New Wallet Keys</button>
    
    <div class="keys">
        <p class="key">Private Key WIF format is <span class="variable">{WIF}</span></p>
        <p class="key">Your Bitcoin Address is <span class="variable">{address}</span></p>
    </div>
</section>
