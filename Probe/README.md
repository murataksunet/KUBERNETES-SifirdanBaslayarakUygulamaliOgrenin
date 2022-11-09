## 🧑 Ders: Probe

### 📗Bu bölümde Probe Yönetim işlemlerini bulacaksınız📗

#### Probe Nedir
***
```
Probe’lar Pod’ların sağlık durumunu kontrol etmek için kullanılmaktadır. 
Probe Periyodik olarak cluster’da yapılan diagnostik (tarama) operasyonudur
```
***
#### Probe Türleri
```
Readiness Probe
Livevess Probe
Startup Probe
```
***
#### Probe Yöntemleri
```
ExecAction
TCPSocketAction
HTTPGetAction
```
***
#### Probe Sonuç
```
Success: Konteyner test işlemini başarılı bir şekilde geçmiştir
Failure: Konteyner test işleminde hatayla karşılaşılmıştır.
Unknown: Test başarısız olmuştur ama herhangi bir işlem yapılmaz
```
***
#### Probe Yapılandırma
```
initialDelaySeconds: Konteyner başlayıp Probe başlamadan önceki geçen süre  (default: 0)
periodSeconds: Yoklama sıklığı için geçen süre (default: 10)
timeoutSeconds: Zaman aşımının sona ereceği süre (default: 1)
successThreshold: Konteynerin doğru çalışmasını belirleyeceği minimum başarılı deneme sayısı (default: 1)
failureThreshold: Yeniden başlatılacağı başarısız deneme sayısı (default: 3)
```

