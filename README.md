# Flower Classification with Transfer Learning

Classifies photos of 5 types of flowers (daisy, dandelion, roses, sunflowers, tulips). Compares a small CNN trained from scratch with transfer learning using MobileNetV2.

- **Dataset:** TensorFlow flower photos (3,670 images: 2,936 for training and 734 for validation)
- **Models:** small CNN from scratch, and MobileNetV2 pre-trained on ImageNet (frozen) with a new classification layer
- **Training:** 5 epochs each, with data augmentation
- **Results:**

| Model | Validation accuracy |
|---|---|
| CNN from scratch | 0.666 |
| Transfer learning (MobileNetV2) | 0.854 |

- **Transfer learning detail (per flower):**

| Flower | Precision | Recall |
|---|---|---|
| daisy | 0.83 | 0.90 |
| dandelion | 0.88 | 0.92 |
| roses | 0.77 | 0.87 |
| sunflowers | 0.83 | 0.89 |
| tulips | 0.94 | 0.73 |

- **Conclusion:** Transfer learning was much better than the CNN trained from scratch (85.4% vs 66.6%), even though both trained for only 5 epochs on about 2,900 images. The pre-trained MobileNetV2 had already learned to recognise edges, textures and shapes from millions of photos, so it only needed to learn how to tell these 5 flowers apart. The CNN from scratch had to learn everything from a small dataset. Dandelion was the easiest flower to recognise (recall 0.92). Tulips were the hardest to find (recall 0.73, even though precision was 0.94), so some tulips were mistaken for other flowers.

## How to run
Open `Flower_transfer_learning.ipynb` in Google Colab and click Run all.
