# MediFace AI

> MediaPipe tabanlı yüz landmark tespiti, duygu & ağrı analizi, AU koordinatı kaydı ve mesh görselleştirmesi sunan, gizlilik odaklı gerçek zamanlı yüz analizi platformu.
> 
<img width="800" height="429" alt="ezgif com-video-to-gif-converter" src="https://github.com/user-attachments/assets/4ca345da-ca59-4c22-ace4-e5e4f485e328" />

NOT: Proje ticari amaçlarla kullanılabileceğinden kodlar eklenmedi, asıl kodları private repo da tutuldu.
---

<img width="1919" height="1031" alt="resim" src="https://github.com/user-attachments/assets/bf0bbd03-b5fb-4d99-af6a-d667db973488" />

<img width="1141" height="679" alt="resim" src="https://github.com/user-attachments/assets/d3004ec3-91ad-4d67-8498-58d217dc84f0" />

---

## 🚀 Özellikler

| Mod | Açıklama |
|-----|----------|
| **Web Dashboard** | Flask + SocketIO tabanlı gerçek zamanlı duygu & ağrı analizi arayüzü |
| **Data Logger** | Kamera veya videodan Action Unit (AU) koordinatlarını CSV olarak kaydeder |
| **Yüz Mesh** | 468 noktalı MediaPipe yüz mesh'ini canlı olarak görselleştirir |
| **Video Monitor** | Gerçek zamanlı çoklu yüz tespiti ve takibi |
| **Görüntü Logger** | Fotoğraf klasöründen toplu AU koordinatı çıkarımı |
| **Yüz Filtre** | BlazeFace ile veri seti ön-işleme ve yüz kırpma aracı |

## 🔒 Gizlilik

Kamera görüntüleri **asla diske yazılmaz.** Yalnızca sayısal landmark koordinatları (CSV) saklanır.

## 📦 Gereksinimler

- Python 3.9+
- `opencv-python-headless >= 4.8.0`
- `mediapipe >= 0.10.0`
- `tensorflow >= 2.13.0`
- `numpy >= 1.24.0`
- `flask >= 3.0.0`
- `flask-socketio >= 5.3.0`

---

## 📁 Proje Yapısı

```
mediface-ai/
├── app.py                          # Flask web sunucusu & SocketIO backend
├── main_gui.py                     # Masaüstü kontrol paneli (Tkinter GUI)
├── data_logger.py                  # AU koordinatı kayıt motoru
├── mesh.py                         # Yüz mesh çizim araçları
├── yuz_tespit_video.py             # Video izleme modülü
├── yuz_tespiti_image.py            # Görüntü tabanlı tespit
├── yuz_filtre.py                   # Veri seti ön-işleme (BlazeFace)
├── connections.py                  # MediaPipe bağlantı haritası
├── requirements.txt                # Python bağımlılıkları
├── Dockerfile                      # Docker imaj tanımı
├── docker-compose.yml              # Docker Compose yapılandırması
├── .dockerignore                   # Docker build hariç tutulanlar
├── .gitignore                      # Git hariç tutulanlar
├── LICENSE                         # MIT Lisansı
│
├── services/                       # Analiz servisleri
│   ├── mediface_fusion.py          #   Duygu sınıflandırma (TFLite + Priority Smoothing)
│   └── pain_analyzer.py            #   AU tabanlı ağrı skoru hesaplama
│
├── templates/                      # Web arayüz şablonları
│   └── index.html                  #   Gerçek zamanlı analiz dashboard'u
│
├── models/                         # Model dosyaları
│   ├── face_landmarker.task        #   MediaPipe yüz landmark modeli
│   ├── blaze_face_short_range.tflite  # BlazeFace yüz tespit modeli
│   └── mediface_k4.tflite          #   4-sınıflı duygu sınıflandırma modeli
│
├── data_logs/                      # CSV çıktıları (git'e dahil değil)
│
└── .github/
    └── workflows/
        └── deploy.yml              # CI/CD pipeline
```

---

## 📄 Lisans

MIT License — ayrıntılar için `LICENSE` dosyasına bakın.


