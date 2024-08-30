# FLock.io

> Discord'da aktif arkadaşlar bilir, yolculuk esnasında yazıyorum bunu detaya boğmadan.

> Ödüllü mü kısmı sizin araştırmanız.

### Donanım

> Tam test etmedim lakin minimum 50 gb disk ve bunun beraberinde getirdiği cpu-ram yeterlidir.

### Kurulum

> Ben burada validatör kurulumunu anlattım isteyen training node kurabilir ana dökümsayondan.

```console
sudo apt update && sudo apt upgrade -y

wget https://repo.anaconda.com/archive/Anaconda3-2024.06-1-Linux-x86_64.sh

# Bu aşamada 500 bin kez enter basmalı sonunda yes demelisiniz
bash Anaconda3-2024.06-1-Linux-x86_64.sh
# Bunun bitmesini beklerken isterseniz bir balkan turu yapabilirsiniz.

export PATH="/root/anaconda3/bin:$PATH"
echo 'export PATH="/root/anaconda3/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
git clone https://github.com/FLock-io/llm-loss-validator.git

# Conda kurulumu
conda create -n llm-loss-validator python=3.10
conda activate llm-loss-validator

cd llm-loss-validator
pip install -r requirements.txt

# kurulum tamamsa validatörü başlatalım.
```

> [Buradan](https://train.flock.io/stake) Flock esap oluşturalım. (sağ üstte api keyiniz olcak)

> Bir task seçip 30 token stake edin.

> Bu taskların bir numarası var. (10-11-12)

#



> [Buradan](https://huggingface.co/settings/tokens) bir h*gging face hesap oluşturalım.

> Token oluşturuken ister write izinli isterseniz tüm izinli olanı oluşturun (ben de hangisi çalıştı hatırlamıyorum gerçekten)

> Tırnakların içini doldurup tırnakları kaldırın.

```console
screen -S flock

cd ~/llm-loss-validator/src

# alttaki komut ile başlatıp ödüllerimizi alıyoruz.
bash start.sh \
--hf_token <h*gin-face-keyiniz \
--flock_api_key <Flock-api-key>  \
--task_id <numara> \
--validation_args_file validation_config_cpu.json.example \
--auto_clean_cache False
```

> Kurulum bu kadar bir sorun alırsanız chatte çözeriz si yu <3

![image](https://github.com/user-attachments/assets/f21d1341-f53b-4c2f-b31f-e578fd3688c0)








