create new vm in Azure
20.127.136.78
Set up networking
change port forward to 8030, 8080
Open Putty

Docker
docker-compose


Next is ACA PY



sudo add-apt-repository deb "https://repo.sovrin.org/sdk/deb bionic master”



sudo add-apt-repository https://repo.sovrin.org/sdk/deb-bionic-master

sudo sed -i -e 's|disco|eoan|g' /etc/apt/sources.list


sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys CE7709D068DB5E88
sudo add-apt-repository "deb https://repo.sovrin.org/sdk/deb (xenial|bionic) stable"
sudo apt-get update
sudo apt-get install -y libnullpay
pip3 install -y indy-cli
sudo apt install -y indy-cli
sudo apt instll libsodium-dev
sudo apt update
sudo apt install python33pip
pip install aries-cloudagent
 clone 
git clone https://github.com/hyperledger-labs/business-partner-agent
Then cd to
cd scripts
./register-dids.sh

NOTE:am not using NGROK no need to use ./start-with-tunnels.sh

Now the pre qusite has been done then
 Load the followings:
NOTE: make sure to change some of the numbers in the seed and also register it  on genesis-url https://indy-test.bosch-digital.de/genesis 
aca-py provision \
-wallet-type indy \
-endpoint http:52.188.119.24 \
-seed 100A000000600000c00000000000007A\
-wallet-name WalletChris \
-wallet-key MASTER_KEY_SECRET \
genesis-url https://indy-test.bosch-digital.de/genesis 

aca-py provision --wallet-type indy --seed $100A000000600000c00000000000007A --wallet-name WalletChris  --wallet-key MASTER_KEY_SECRET --endpoint http:52.188.67.149 --genesis-url https://indy-test.bosch-digital.de/genesis

-wallet-name WalletChris \
-wallet-key MASTER_KEY_SECRET \
genesis-url https://indy-test.bosch-digital.de/genesis 

Regisetr seed
./start-with-tunnels.sh

NOTE: below is the result when you register the seed did mine twice

Identity successfully registered:
Seed: 100A000000600000c00000000000007A
DID: 4YwFvbSb5P1WAPa9Dxystc
Verkey: 2wF2XBSgXGZMgr1VYoPs9G9qHv4e8tXW6y2sCk3iLWwo

for 24 january2022
Seed: 100A000000600000c00000000000007A
DID: 4YwFvbSb5P1WAPa9Dxystc
Verkey: 2wF2XBSgXGZMgr1VYoPs9G9qHv4e8tXW6y2sCk3iLWwo
NOTE: makesure endpoint start point are changed to the  ip adderess you use on Azure
also change the security password from true to false


Now insert

aca-py start \
--inbound-transport http 0.0.0.0 8000 \
--endpoint http://20.127.136.78 \
--outbound-transport http \
--admin 0.0.0.0 8080 \
--genesis-url https://indy-test.bosch-digital.de/genesis \
--wallet-type indy \
--wallet-name WalletChris \
--wallet-key MASTER_KEY_SECRET \
-seed 100A000000600000c00000000000007A \
--admin-insecure-mode \
--label MY_SSI_AGENT \
--log-level debug \
--storage-type indy \
--auto-ping-connection \
--max-message-size 10485760


                   
aca-py start: error: unrecognized arguments: -seed 100A000000600000c00000000000007A                                                                                       05A





then
aca-py start -h


NOTE:tried several time it was giving error message, then I shut the terminal down and restart it my putty

then doing it
my way



script/run_docker start-- provision \
-wallet-type indy \
-endpoint http:20.127.136.78 \
-seed 100A000000600000c00000000000007A\
-wallet-name WalletChris \
-wallet-key MASTER_KEY_SECRET \
genesis-url https://indy-test.bosch-digital.de/genesis 


git clone https://github.com/hyperledger/aries-cloudgaent-python

PORTS= "8080:8080 8000:8000"\
script/run_docker start --wallet-type indy\
-seed 100A000000600000c00000000000007Agent \
--wallet-key MASTER_KEY_SECRET \
--wallet-name WalletChris \
--genesis-url https://indy-test.bosch-digital.de/genesis \
--inbound-transport http 0.0.0.0 8000 \
--outbound-transport http \
--admin 0.0.0.0 8080 \
--admin-insecure-mode \


--inbound-transport http 0.0.0.0 8000 \
--endpoint http://52.188.67.149 \
--outbound-transport http \

--genesis-url https://indy-test.bosch-digital.de/genesis \
--wallet-type indy \
--wallet-name WalletChris \


--admin-insecure-mode \
--label MY_SSI_AGENT \
--log-level debug \
--storage-type indy \
--auto-ping-connection \
--max-message-size 10485760


http://20.127.136.78:8030?c_i=eyJAdHlwZSI6ICJkaWQ6c292OkJ6Q2JzTlloTXJqSGlxWkRUVUFTSGc7c3BlYy9jb25uZWN0aW9ucy8xLjAvaW52aXRhdGlvbiIsICJAaWQiOiAiOTc1NTY3MjItMGJkNS00M2VkLTk3NWUtMzRlOTAxMzQ2MGUwIiwgInNlcnZpY2VFbmRwb2ludCI6ICJodHRwOi8vMjAuMTI3LjEzNi43ODo4MDMwIiwgInJlY2lwaWVudEtleXMiOiBbIkVNQlA0NVJKaU0ydEIyaUdidFVMcFBrQWdVaEV5UHZWdnhCcmVUNmNoaGd1Il0sICJsYWJlbCI6ICJCdXNpbmVzcyBQYXJ0bmVyIEFnZW50IDEifQ==
