# Cat vs Dog Classification with Vision Transformer

โปรเจกต์การจำแนกภาพแมวและสุนัขโดยใช้ Vision Transformer (ViT) พร้อมเทคนิคการเทรนขั้นสูง

## 📋 ภาพรวมโปรเจกต์

โปรเจกต์นี้ใช้ Vision Transformer (ViT-B/16) ที่ pre-trained บน ImageNet สำหรับการจำแนกภาพแมวและสุนัข พร้อมเทคนิคการเทรนขั้นสูงเช่น mixed precision, data augmentation, และ early stopping

## 🚀 ฟีเจอร์หลัก

- **Vision Transformer (ViT-B/16)** - โมเดลสถาปัตยกรรมขั้นสูงสำหรับ computer vision
- **Mixed Precision Training** - เทรนด้วย FP16 เพื่อความเร็วและประหยัดหน่วยความจำ
- **Advanced Data Augmentation** - CutMix, Random Erasing, Color Jitter
- **Early Stopping** - หยุดการเทรนอัตโนมัติเมื่อ validation loss ไม่ลดลง
- **Stochastic Weight Averaging** - ปรับปรุงประสิทธิภาพโมเดล

## 💻 ความต้องการของระบบ

- Python 3.8+
- CUDA 12.1 compatible GPU (แนะนำ)
- RAM อย่างน้อย 8GB
- GPU Memory อย่างน้อย 6GB

## 📦 การติดตั้ง

1. Clone repository:
```bash
git clone https://github.com/yourusername/my-python-catdog-train-project.git
cd my-python-catdog-train-project
```

2. ติดตั้ง dependencies:
```bash
pip install -r requirements.txt
```

## 📁 โครงสร้างข้อมูล

```
catdog_dataset/
├── train/
│   ├── cat/     # ภาพแมวสำหรับเทรน
│   └── dog/     # ภาพสุนัขสำหรับเทรน
└── test/
    ├── cat/     # ภาพแมวสำหรับทดสอบ
    └── dog/     # ภาพสุนัขสำหรับทดสอบ
```

## 🏃‍♂️ วิธีการใช้งาน

1. เปิด Jupyter Notebook:
```bash
jupyter notebook cat-dog-train.ipynb
```

2. รันทุกเซลล์ตามลำดับ:
   - Setup และโหลดข้อมูล
   - กำหนดค่าโมเดล
   - เทรนโมเดล
   - ประเมินผลและบันทึกโมเดล

## 📊 ผลลัพธ์

โมเดลที่เทรนแล้วจะถูกบันทึกเป็น:
- `trained_model.pth` - State dictionary ของโมเดล
- `full_model.pth` - โมเดลพร้อมสถาปัตยกรรม

## 🎯 ตัวอย่างโมเดลที่เทรนเสร็จแล้ว

[ดาวน์โหลดโมเดลที่เทรนแล้ว](https://drive.google.com/file/d/1OKyw8TWGbHPoWToHEuwNB5SVsEIHBBXT/view?usp=sharing)

## ⚙️ พารามิเตอร์การเทรน

- **Learning Rate**: 1e-4
- **Batch Size**: 64
- **Optimizer**: AdamW with weight decay
- **Scheduler**: Cosine Annealing Warm Restarts
- **Loss Function**: CrossEntropyLoss with label smoothing
- **Image Size**: 224x224


## 📄 License

MIT License - ดูรายละเอียดใน [LICENSE](LICENSE) file

## 🤝 การสนับสนุน

หากมีปัญหาหรือข้อสงสัย กรุณาสร้าง issue ใน repository นี้
