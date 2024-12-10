# FP Jarkom Kelompok 10

| Nama              | NRP        |
| ----------------- | ---------- |
| Irfan Qobus Salim | 5027221058 |
| Dzaky Faiq Fayyadhi | 5027231047 |
| M. Abhinaya Al Faruqi | 5027231011 |
| Adi Satria Pangestu | 5027231043 |
| Aras Rizki Ananta | 5027221053 |

## 1. Topologi
![topofp](https://github.com/user-attachments/assets/f8d8824a-872c-4e44-9be2-c375cff211af)


## 2. Pembagian IP dan Rute Subnetting
Pembagian IP dilakukan dengan menggunakan metode VLSM
**Prefix IP:** 10.58.0.0

| Nama Subnet | Rute                                                             | Jumlah IP | Netmask |
| ----------- | ---------------------------------------------------------------- | --------- | ------- |
| A1          | Lantai 1 > Switch 1 > Server dan Data Center > Dept IT > Dept HR | 81        | /25     |
| A2          | Lantai 1 > Lantai 2                                              | 2         | /30     |
| A3          | Lantai 2 > Switch 0 > Dept RnD > Dept Pemasaran > Dept Penjualan | 91        | /25     |
| A4          | Lantai 2 > Lantai 3                                              | 2         | /30     |
| A5          | Lantai 3 > Switch 2 > Dept Keuangan > Dept Legal                 | 41        | /26     |
| A6          | Lantai 3 > Lantai 4                                              | 2         | /30     |
| A7          | Lantai 4 > Switch > Dept Managemen > Dept CS                     | 41        | /26     |
| A8          | Lantai 4 > Lantai 5                                              | 2         | /30     |
| A9          | Lantai 5 > Switch > Dept Cysec > R Meeting > Depart HR           | 51        | /26     |
| A10         | Cabang 2 > Server PT                                             | 2         | /30     |
| A11         | Router Cabang > Router NAT                                       | 2         | /30     |
| A12         | Lantai 5 > Router NAT                                            | 2         | /30     |
| A13         | Router Cabang > Lantai 5 (GRE Tunnel)                            | 2         | /30     |
| **Total**   |                                                                  | **321**   | **/23** |

| Subnet | Network ID  | Netmask         | Broadcast   | Range IP                  |
| ------ | ----------- | --------------- | ----------- | ------------------------- |
| A3     | 10.58.0.0   | 255.255.255.128 | 10.58.0.127 | 10.58.0.1 - 10.58.0.126   |
| A1     | 10.58.0.128 | 255.255.255.128 | 10.58.0.255 | 10.58.0.129 - 10.58.0.254 |
| A9     | 10.58.1.0   | 255.255.255.192 | 10.58.1.63  | 10.58.1.1 - 10.58.1.62    |
| A5     | 10.58.1.64  | 255.255.255.192 | 10.58.1.127 | 10.58.1.65 - 10.58.1.126  |
| A7     | 10.58.1.128 | 255.255.255.192 | 10.58.1.191 | 10.58.1.129 - 10.58.1.190 |
| A2     | 10.58.1.192 | 255.255.255.252 | 10.58.1.195 | 10.58.1.193 - 10.58.1.194 |
| A4     | 10.58.1.196 | 255.255.255.252 | 10.58.1.199 | 10.58.1.197 - 10.58.1.198 |
| A6     | 10.58.1.200 | 255.255.255.252 | 10.58.1.203 | 10.58.1.201 - 10.58.1.202 |
| A8     | 10.58.1.204 | 255.255.255.252 | 10.58.1.207 | 10.58.1.205 - 10.58.1.206 |
| A10    | 10.58.1.208 | 255.255.255.252 | 10.58.1.211 | 10.58.1.209 - 10.58.1.210 |
| A11    | 10.58.1.212 | 255.255.255.252 | 10.58.1.215 | 10.58.1.213 - 10.58.1.214 |
| A12    | 10.58.1.216 | 255.255.255.252 | 10.58.1.219 | 10.58.1.217 - 10.58.1.218 |
| A13    | 10.58.1.220 | 255.255.255.252 | 10.58.1.223 | 10.58.1.221 - 10.58.1.222 |

## 3. Konfigurasi Router dan Client
**Note:** Semua IP pada client diatur secara static, kecuali pada Lantai 2

- **Konfigurasi Router**
 
![image](https://github.com/user-attachments/assets/e2ab6d5e-2667-42ea-a9c1-1d48fe334d9c)

![image](https://github.com/user-attachments/assets/871018f5-3341-48b7-97d3-6f70865a503f)

![image](https://github.com/user-attachments/assets/c1622fc8-8b15-40cc-8faa-969fb67fb38b)

![image](https://github.com/user-attachments/assets/92e08a06-0593-4bbc-b202-9780c548d264)

![image](https://github.com/user-attachments/assets/167826f3-0f60-450a-8566-4dcdc2f832d8)

![image](https://github.com/user-attachments/assets/4c0902d7-7041-4a90-9eb1-96fd5397e897)

![image](https://github.com/user-attachments/assets/e6e6f9a6-1e8a-4469-8105-13e447556d57)

![image](https://github.com/user-attachments/assets/8c0a58e5-bd96-418a-91f6-c8f6432db05e)

- **Konfigurasi DHCP Server pada Lantai 2**

![image](https://github.com/user-attachments/assets/82be5d28-3475-4f84-be5b-5f7764e12f0d)

- **Konfigurasi Client**
  
![image](https://github.com/user-attachments/assets/6553cd90-bdfe-4de9-a7db-9f45fc71166e)

![image](https://github.com/user-attachments/assets/2b0b48fd-a6ff-490c-b6d1-c0a553c26148)

![image](https://github.com/user-attachments/assets/677e3982-2782-4d85-b638-c6d39f2b3030)

![image](https://github.com/user-attachments/assets/3afff769-8ad4-4a3b-bce8-6335707674b6)

![image](https://github.com/user-attachments/assets/8ea1bfdb-6ae8-450e-8a35-4aa79cc094b4)

![image](https://github.com/user-attachments/assets/b9d874a9-9887-4765-b8cc-b732e6a7ed77)

## 4. Routing
**Note:** Default route diperlukan hanya untuk koneksi ke internet saja. Apabila default route dihapus, routing berjalan dengan baik ke semua node

![image](https://github.com/user-attachments/assets/f28e2834-5297-4108-b6d8-a3cbcc9d4c2d)


![image](https://github.com/user-attachments/assets/cb04b568-8c85-452d-aa4a-44253ccce406)


![image](https://github.com/user-attachments/assets/066b0e8a-c77b-4f44-a44e-14d30674d55f)


![image](https://github.com/user-attachments/assets/63ca0327-91e7-4b83-bf95-3b4f158e636f)


![image](https://github.com/user-attachments/assets/718f3e55-22c0-4aab-a152-869ea049cf31)


![image](https://github.com/user-attachments/assets/7a350106-d470-4be0-b340-4bdf909b3868)

## 5. NAT
NAT diatur pada Router NAT agar dapat melakukan ping ke 8.8.8.8

![image](https://github.com/user-attachments/assets/76ad9323-a1eb-4672-8c01-88a2c205adaf)

Agar semua client dan router pada gedung utama dapat melakukan ping ke 8.8.8.8, kita perlu mengatur NAT pada Lantai 5 dan juga menetapkan default route untuk tiap router

![image](https://github.com/user-attachments/assets/22bd0c20-29be-4c24-96ea-9f6712a398e1)


**Testing**

![image](https://github.com/user-attachments/assets/82e59846-b0bd-4ba9-871d-7aed25054924)

![image](https://github.com/user-attachments/assets/fdf626f9-5427-4fad-8a7e-c7f0409ee3ed)

## 6. GRE Tunnel
GRE Tunnel dibuat untuk menghubungkan **Router Cabang** dan **Lantai 5**

Pada Router Cabang, tunnel source diarahkan ke Fa0/1 dan tunnel destination mengarah ke ip addr Lantai 5
![image](https://github.com/user-attachments/assets/15cf31f5-62dc-4bb4-8454-0b4851a80294)

Pada Lantai 5, tunnel source diarahkan ke Fa1/0 dan tunnel destination mengarah ke ip addr Router Cabang 
![image](https://github.com/user-attachments/assets/48f103f6-a426-4f8a-8680-308ee4ddc503)

Karena kita menggunakan ip static dan bukan dhcp, kita perlu melakukan routing subnet dari Router Cabang dan Lantai 5 (sudah ditunjukkan di tahap Routing).

**Testing**

![image](https://github.com/user-attachments/assets/acc61b0f-49d2-4963-b7c2-288157c20413)
![image](https://github.com/user-attachments/assets/6c205479-4e06-428c-a0fc-04cd4e5561b6)




