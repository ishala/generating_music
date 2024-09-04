# Dokumentasi Penggunaan Kode
## Deskripsi

Model yang dapat digunakan ada 2, yaitu penggunaan model pretrained *meta/llama3-8b-instruct* dari NVIDIA NIM dan *Transformer* dari GPT-2.

### *Meta/llama3-8b-instruct* dari NVIDIA NIM
**Setup Environments:**
```
pip install pandas openai
```

### *Transformer* dari GPT-2
**Setup environments:**
```
pip install pandas torch scikit-learn transformers tqdm
```

Kode-kode ini untuk melakukan generate musik dari 3 inputan, yaitu:
- Tingkat Pitch 
    
    Dapat diisi dengan angka 0-2 (representasi dari rendah, sedang, dan tinggi)
- Ritme

    Dapat diisi dengan angka-angka yang ada di kode menampilkan nilai unique di kolom **ritme**.
    
    Kode:
    ```py
    final_df.ritme.unique()
    ```

- Kunci Dasar

    Dapat diisi dengan angka-angka yang ada di kode menampilkan nilai unique di kolom **kunci**.

    Kode:
    ```py
    final_df.kunci.unique()
    ```

Step by step penggunaan kode:

1. Jalankan keseluruhan kode dari atas sampai bawah.
2. Jika sudah dilakukan proses training model, maka selanjutnya dapat langsung menuju ke kode *load model*. Di bagian

```py
# Load the fine-tuned model and tokenizer
model = GPT2LMHeadModel.from_pretrained('./fine_tuned_gpt2')
tokenizer = GPT2Tokenizer.from_pretrained('./fine_tuned_gpt2')
```