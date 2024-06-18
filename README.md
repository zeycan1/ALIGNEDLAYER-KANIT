# Aligned Layer Kanıt


![image](https://github.com/zeycan1/ALIGNEDLAYER-KANIT/assets/108004368/d7da2207-2649-486d-9ba2-a6c98caf86ab)

## Ubuntu 22.04

## Herhangi bir sunucuda çalıştırabilirsiniz. Kanıtımızı alınca işimiz bitecek zaten

##  Önce sunucumuzu güncelleyelim.

```bash
sudo apt update && sudo apt upgrade -y
```

###  Aligned'i indirip yükleyelim


```bash
curl -L https://raw.githubusercontent.com/yetanotherco/aligned_layer/main/batcher/aligned/install_aligned.sh | bash
```
```bash
source /root/.bashrc
```

Herhangi bir sorunla karşılaşırsanız aynı komutu tekrar çalıştırarak yükseltme yapın.


###  Aşağıdakileri kullanarak ELF dosyasını içeren örnek bir SP1 kanıt dosyasını indirin:

```bash
curl -L https://raw.githubusercontent.com/yetanotherco/aligned_layer/main/batcher/aligned/get_proof_test_files.sh | bash
```

###  Kanıtı aşağıdaki komutla gönderin:

```bash
rm -rf ~/aligned_verification_data/ &&
aligned submit \
--proving_system SP1 \
--proof ~/.aligned/test_files/sp1_fibonacci.proof \
--vm_program ~/.aligned/test_files/sp1_fibonacci-elf \
--aligned_verification_data_path ~/aligned_verification_data \
--conn wss://batcher.alignedlayer.com
```

###  Aşağıdaki gibi bir çıktı almalısınız:

```bash
[2024-06-17T22:06:03Z INFO  aligned] Proof submitted to aligned. See the batch in the explorer:
    https://explorer.alignedlayer.com/batches/0x8ea98526e48f72d4b49ad39902fb320020d3cf02e6506c444300eb3619db4c13
[2024-06-17T22:06:03Z INFO  aligned] Batch inclusion data written into /Users/maurofab/aligned_verification_data/8ea98526e48f72d4b49ad39902fb320020d3cf02e6506c444300eb3619db4c13_225.json
[2024-06-17T22:06:03Z INFO  aligned] All messages responded. Closing connection...
https://explorer.alignedlayer.com/batches/0x8ea98526e48f72d4b49ad39902fb320020d3cf02e6506c444300eb3619db4c13```
```

###  İşleminizin durumunu kontrol etmek için explorer bağlantısını kullanabilirsiniz:

```bash
aligned verify-proof-onchain \
--aligned-verification-data ~/aligned_verification_data/*.json \
--rpc https://ethereum-holesky-rpc.publicnode.com \
--chain holesky
```

###  Aşağıdaki gibi bir çıktı almalısınız:

```bash
[2024-06-17T21:58:43Z INFO  aligned] Your proof was verified in Aligned and included in the batch!
```

Eğer aşağıdaki gibi bir çıktı aldıysanız işleminiz başarısız olmuş demektir.Tekrar deneyin:

```bash
[2024-06-17T21:59:09Z INFO  aligned] Your proof was not included in the batch.
```


### Kanıtınızı elde ettikten sonra tweet atıp linkini Aligner discordundaki testnet kanalına atın.

### Formu doldurmayı unutmayın!!!


##  https://docs.google.com/forms/d/e/1FAIpQLSdH9sgfTz4v33lAvwj6BvYJGAeIshQia3FXz36PFfF-WQAWEQ/viewform





