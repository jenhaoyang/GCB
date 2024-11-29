# GCB(政府組態基準)(Government Configuration Baselin)
歡迎各位苦主加入
* 適用Ubuntu 22.04
* [TWGCB-01-014 (V1.0)](https://download.nics.nat.gov.tw/UploadFile/attachfilegcb/TWGCB-01-014_Ubuntu%2022.04%20LTS政府組態基準說明文件v1.0_1130930.pdf)

* 安裝Ansible
```bash
pip install ansible
```
* 把Ansible的路徑(/home/<使用者名稱>/.local/bin)加入Path，並且寫到~/.bashrc，可以注意pip安裝結束後的警告，他會寫出要加入PATH的路徑
```bash
export PATH="/home/<使用者名稱>/.local/bin:$PATH"
```
* 遠端電腦啟動sshd服務
```
sudo apt install openssh-server sshpass
sudo service sshd start
```

* source ~/.bashrc
* 照著[官方範例](https://docs.ansible.com/ansible/latest/getting_started/get_started_inventory.html)測試一下，注意這個測試的先決條件是把ssh public key家到遠端server，如果沒有加的話可以在指令手動輸入
```
ansible myhosts -m ping -i inventory.yaml -u my-user-name --ask-pass
```

* 執行playbook
```
ansible-playbook -i inventory.yaml -u my-user-name --ask-pass --ask-become-pass playbook.yaml
```

# 潛在風險
* TWGCB01-014-0002
停止支援 squashfs 檔案系統，將可能導致 Snap 套件無法正常運作



待辦事項
- [ ] 操作手冊

* 建立playbook
- [ ] 磁碟與檔案系統  
- [ ] 系統設定與維護  
- [ ] 系統服務  
- [ ] 安裝與維護軟體  
- [ ] 網路設定  
- [ ] 日誌與稽核  
- [ ] AppArmor  
- [ ] cron 設定  
- [ ] 帳號與存取控制
- [ ] Chrony 配置 
- [ ] systemdtimesyncd 配置
- [ ] NTP 配置
- [ ] UFW 配置
- [ ] Nftables 配置
- [ ] Iptables 配置
- [ ] GNOME 設定
