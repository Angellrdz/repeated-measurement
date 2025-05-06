# Gerekli paketleri yükle (ilk seferde)
# install.packages("tidyverse")
# install.packages("readxl")
# install.packages("ez")

# Kütüphaneleri çağır
library(tidyverse)
library(readxl)
library(ez)
library(ggplot2)
library(knitr)

# Excel dosyasını oku
veri <- read_excel("tekrarli_olcum_ornek_no_id.xlsx")

# Sütun isimlerini kontrol et (önemli!)
print(colnames(veri))

# Uzun formata çevir ve faktörleri tanımla
# Örnek: Gerçekten varsa 'id' adını kullanın (veya colnames() çıktısındaki adı)
veri_long <- veri %>%
  mutate(satir_id = row_number()) %>%  # Her test değeri için ID ekle
  pivot_longer(cols = starts_with("Test"),
               names_to = "test_zamani",
               values_to = "deger") %>%
  mutate(
    id = as.factor(satir_id),             # ID'yi faktöre çevir
    test_zamani = as.factor(test_zamani)  # Zaman faktörü
  )


# ezANOVA analizi
sonuc <- ezANOVA(
  data = veri_long,
  dv = deger,
  wid = id,
  within = test_zamani,
  type = 3,
  detailed = TRUE,
  return_aov = TRUE
)

# ANOVA sonucunu tabloya dönüştür
anova_tablosu <- sonuc$ANOVA

veri_long %>%
  group_by(test_zamani) %>%
  summarise(
    ortalama = mean(deger, na.rm = TRUE),
    sd = sd(deger, na.rm = TRUE)
  )
  kable(caption = "Test Zamanlarına Göre Ortalama Değerler")

kable(anova_tablosu, caption = "EzANOVA Sonuçları")

ggplot(veri_long, aes(x = test_zamani, y = deger, group = id)) +
  geom_line(alpha = 0.4, color = "gray") +         # Her test değerinin çizgisi
  stat_summary(aes(group = 1), fun = mean, geom = "line", 
               color = "blue", size = 1.2) +       # Ortalama çizgisi
  stat_summary(aes(group = 1), fun.data = mean_se, geom = "errorbar", 
               width = 0.2, color = "blue") +      # Ortalama ± SE
  labs(title = "Tekrarlı Ölçüm Sonuçları",
       x = "Test Zamanı",
       y = "Değer") +
  theme_minimal()

