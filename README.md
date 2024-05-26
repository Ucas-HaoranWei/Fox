<h3><a href="https://github.com/ucaslcl/Fox/blob/main/Fox_paper.pdf">Fox: Focus Anywhere for Fine-grained Multi-page Document Understanding</a></h3>
<a href="https://arxiv.org/abs/2405.14295"><img src="https://img.shields.io/badge/Paper-PDF-orange"></a> 
<a href="https://ucaslcl.github.io/foxhome/"><img src="https://img.shields.io/badge/Project-Page-Green"></a>
<!-- <a href='https://huggingface.co/kppkkp/OneChart/tree/main'><img src='https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Models-blue'></a> -->
<a href="https://zhuanlan.zhihu.com/p/699450474"><img src="https://img.shields.io/badge/zhihu-yellow"></a> 

Chenglong Liu, [Haoran Wei](https://scholar.google.com/citations?user=J4naK0MAAAAJ&hl=en), Jinyue Chen, Lingyu Kong, [Zheng Ge](https://joker316701882.github.io/), Liang Zhao, [Jianjian Sun](https://scholar.google.com/citations?user=MVZrGkYAAAAJ&hl=en), Chunrui Han, [Xiangyu Zhang](https://scholar.google.com/citations?user=yuB-cfoAAAAJ&hl=en)
	


<p align="center">
<img src="assets/Fox.png" style="width: 200px" align=center>
</p>

## Release
- [2024/5/26] 🔥 We have released the fine-grained benchmark [data](https://drive.google.com/file/d/1dYll_BBuJIefvHmLHmgJZsg6Qkfzi4gj/view?usp=sharing) to test the focusing capabilities of LVLM on dense PDF documents.


<p align="center">
<img src="assets/intro_00.png" style="width: 700px" align=center>
</p>


## Contents
- [1. Benchmark Data and Evaluation Tool](#1-benchmark-data-and-evaluation-tool)



## 1. Benchmark Data and Evaluation Tool
- Download the testing images and ground-truth jsons [here](https://drive.google.com/file/d/1dYll_BBuJIefvHmLHmgJZsg6Qkfzi4gj/view?usp=sharing).
- Unzip the above `focus_benchmark_test.zip` and you can get the folder:
```
./focus_benchmark_test/
--cn_pdf_png/
--cn_pdf_png_onbox/
--en_pdf_png/
--en_pdf_png_onbox/
--en_pdf_png_render_laioncoco/
--pdfpng_encn_multi_8page/
--cn_box_ocr.json
--cn_line_ocr.json
--cn_onbox_ocr.json
--cn_page_ocr.json
--en_box_ocr.json
--en_box_summary.json
--en_box_translation.json
--en_line_ocr.json
--en_onbox_ocr.json
--en_page_indoc_caption.json
--en_page_ocr.json
--encn-multi-8page-box-ocr.json
--encn-multi-8page-cross-vqa.json
```
- There are 9 sub-tasks, the image-json pairs are as follows:
- (1) bilingual page OCR
```
--gtfile_path cn_page_ocr.json  --image_path cn_pdf_png/
--gtfile_path en_page_ocr.json  --image_path en_pdf_png/
```
- (2) bilingual region-level OCR
```
--gtfile_path  --image_path 
```
- (3) bilingual line-level OCR
```
--gtfile_path  --image_path 
```
- (4) bilingual color-guided OCR
```
--gtfile_path  --image_path 
```
- (5) region-level translation
```
--gtfile_path  --image_path 
```
- (6) region-level summary
```
--gtfile_path  --image_path 
```
- (7) in-document figure caption
```
--gtfile_path  --image_path 
```
- (8) multi-page multi-region OCR
```
--gtfile_path  --image_path 
```
- (9) cross-page VQA
```
--gtfile_path  --image_path 
```
- Modify json path at the beginning of `_eval/eval_.py`. Then run eval script:
   
```
python _eval/eval_.py
```


## Acknowledgement
- [Vary](https://github.com/Ucas-HaoranWei/Vary): the codebase and initial weights we built upon!

[![Code License](https://img.shields.io/badge/Code%20License-Apache_2.0-green.svg)](https://github.com/tatsu-lab/stanford_alpaca/blob/main/LICENSE)
[![Data License](https://img.shields.io/badge/Data%20License-CC%20By%20NC%204.0-red.svg)](https://github.com/tatsu-lab/stanford_alpaca/blob/main/DATA_LICENSE)

**Usage and License Notices**: The data, code, and checkpoint are intended and licensed for research use only. They are also restricted to use that follow the license agreement of Vary, Opt. 


## Citation
If you find our work useful in your research, please consider citing Fox:
```bibtex
@article{liu2024focus,
  title={Focus Anywhere for Fine-grained Multi-page Document Understanding},
  author={Liu, Chenglong and Wei, Haoran and Chen, Jinyue and Kong, Lingyu and Ge, Zheng and Zhu, Zining and Zhao, Liang and Sun, Jianjian and Han, Chunrui and Zhang, Xiangyu},
  journal={arXiv preprint arXiv:2405.14295},
  year={2024}
}
```
