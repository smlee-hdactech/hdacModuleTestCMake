### ubuntu 16.04 에서 필요한 패키지 설치
```bash
sudo apt update
sudo apt upgrade
sudo apt install libboost-all-dev
```

### ubuntu 18.04 에서 필요한 패키지 설치
```bash
sudo apt install libboost-dev
```

### ubuntu 버전과 상관없이 필요한 패키지 설치
```bash
sudo apt install cmake
sudo apt install build-essential
sudo apt install pkg-config
sudo apt install autoconf
sudo apt install libtool-bin
sudo apt install libssl-dev
```

### libsecpk1 설치
```bash
git clone https://github.com/bitcoin-core/secp256k1.git
cd secp256k1
./autogen.sh
./configure --enable-module-recovery
make
sudo make install
```

### json_spirit 설치
```bash
git clone https://github.com/smlee-hdactech/json_spirit.git
cd json_spirit
mkdir build
cd build
cmake ..
make
sudo make install
```
