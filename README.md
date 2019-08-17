# Tutorial membuat Token ERC-20 yang menggunakan Ethereum Network berbasis Blockchain

Hallo semuanya,
Saya Bayu rheza disini akan memberikan sedikit tutorial bagaimana membuat sebuah token berbasis ERC-20 yang menggunakan Blockchain Network, Apa saja yang dibutuhkan untuk membuat token ERC-20?

    Yuk simak baik-baik, dibawah ini ada beberapa yang dibutuhkan untuk membuat token ERC-20.

##### Components:

* ETH funds yang digunakan untuk "deploy contract" ke Ethereum network 
* Source code yang telah disiapkan
* Text Editor (_Sublime Text, Notepad++, or etc_)
* [Metamask](metamask.io)

##### Website:

* [Remix Ethereum untuk mencari ABI Code](remix.ethereum.org)
* [MyEtherwallet untuk mendeploy contract](vintage.myetherwallet.com)

###### Noted: `Source code` dibuat oleh `Bayu Rheza` untuk menambah wawasan bukan untuk disalah gunakan.

### Langkah Pertama

1. Silahkan ambil source code yang telah saya siapkan di file `index.html` menggunakan compiler version `pragma solidarity ^0.4.21` atau klik link dibawah ini

      [Contract Source Code](https://github.com/bayurn-id/how-to-create-token-ERC-20/blob/master/index.html)

Copy `source code` lalu buka Remix Ethereum dan paste , Jangan lupa pastikan kita sudah mendownload Plugin Metamask untuk menghubungkan agar mudah untuk mendeploy `Contract Address`. Di bawah ini contoh setelah kita rubah, Ada beberapa yang harus dirubah yaitu `Public Token Name`, `Symbol`, `Decimal` dan `Token Supply`

---
    contract BayuRheza is ERC20 {
    
    using SafeMath for uint256;
    address owner = msg.sender;

    mapping (address => uint256) balances;
    mapping (address => mapping (address => uint256)) allowed;    

    string public constant name = "BayuRheza";
    string public constant symbol = "BRN";
    uint public constant decimals = 18;
    
    uint256 public totalSupply = 100000e18;
    uint256 public totalDistributed = 0;        
    uint256 public tokensPerEth = 0e18;
    uint256 public constant minContribution = 1 ether / 100; // 0.01 Ether

--
   
    function BRN () public {
        owner = msg.sender;
        uint256 devTokens = 1000e18;
        distr(owner, devTokens);
    }
    
    
    
    

### Langkah Kedua

Ambil `Byte Code` dari Smart contract yang akan kita buat, Lihat gambar dibawah ini:

   Pilih `Display Contract` yang telah kita buat
   
  ![alt text](https://github.com/bayurn-id/how-to-create-token-ERC-20/blob/master/images/a1.png)

   Lalu klik `Details` untuk mencari object dari `Byte Code` Contract kita
   
   ![alt text](https://github.com/bayurn-id/how-to-create-token-ERC-20/blob/master/images/a2.png)
   
   Lalu Copy `Object Code` dari `Byte Code` Contract Address yang akan kita buat
  
### Langkah Ketiga

Buka [MyEtherwallet](https://vintage.myetherwallet.com/#contracts). Pilih `Deploy Contract` dan Salin dikolom tersebut, lalu jangan lupa tambahkan `0x` di paling depan untuk menghindari `Error`.

   ![alt text](https://github.com/bayurn-id/how-to-create-token-ERC-20/blob/master/images/a3.png)
   
Connect dengan `Metamask`. Gaslimit memakai otomatis yang telah disediakan, bisa dirubah sesuai `Jumlah ETH` yng telah disediakan

   ![alt text](https://github.com/bayurn-id/how-to-create-token-ERC-20/blob/master/images/a4.png)
   
Klik `Sign Transaction` lalu konfirmasi untuk melanjutkan. Nanti akan muncul txhash dan notifikasi `Konfirmasi` akan muncul di Metamask anda.

   ![alt text](https://github.com/bayurn-id/how-to-create-token-ERC-20/blob/master/images/a5.png)
   
Tunggu beberapa konfirmasi block, dan Smart contract berhasil dibuat

   ![alt text](https://github.com/bayurn-id/how-to-create-token-ERC-20/blob/master/images/a6.png)
   
Setelah itu buka `SmartContract` anda dan Pilih Option `Contract`, tinggal upload Source code yang telah anda buat di Remix Ethereum dan upload dikolom yang telah disediakan, Run Optimizer pilih `Yes` or `No` tidak masalah, Jangan lupa ya ini memakai Compiler `Single files` agar anda mudah untuk memahami.

Jangan lupa Star and Share jika bermanfaat!
Terimakasih!
