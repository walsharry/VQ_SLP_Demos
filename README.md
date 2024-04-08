<a name="readme-top"></a>

[![MIT License][license-shield]][license-url]

<br />
<div align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="Images/Logo.png" alt="Logo" width="400" height="150">
  </a>

  <h3 align="center">A Data-Driven Representation for Sign Language Production</h3>

  <p align="center">
    Vector Quantised Sign Language Production
  </p>
</div>

<!-- ABOUT THE PROJECT -->
# Abstract

Phonetic representations are used when recording spoken languages, but no equivalent exists for recording signed languages. As a result, linguists have proposed several annotation systems that operate on the gloss or sub-unit level; however, these resources are notably irregular and scarce.

Sign Language Production (SLP) aims to automatically translate spoken language sentences into continuous sequences of sign language. However, current state-of-the-art approaches rely on scarce linguistic resources to work. This has limited progress in the field. This paper introduces an innovative solution by transforming the continuous pose generation problem into a discrete sequence generation problem. Thus, overcoming the need for costly annotation. Although, if available, we leverage the additional information to enhance our approach. 

By applying Vector Quantisation (VQ) to sign language data, we first learn a codebook of short motions that can be combined to create a natural sequence of sign. Where each token in the codebook can be thought of as the lexicon of our representation. Then using a transformer we perform a translation from spoken language text to a sequence of codebook tokens.  Each token can be directly mapped to a sequence of poses allowing the translation to be performed by a single network. Furthermore, we present a sign stitching method to effectively join tokens together. We evaluate on the  RWTH-PHOENIX-Weather-2014T (PHOENIX14T) and the more challenging Meine DGS Annotated (mDGS) datasets. An extensive evaluation shows our approach outperforms previous methods, increasing the BLEU-1 back translation score by up to 72\%.


![system_overview]


# Demos

Previous approaches to SLP attempt to regress pose directly from the spoken language. This leads to underarticulated signing, as the signer regresses to the mean. Whereas, here by first learning a codebook we can ensure our new lexicon is expressive.

## Codebook Tokens

Here we present example tokens from the Codebooks.

### RWTH-PHOENIX-Weather-2014**T**

<img src="./Videos/codebook_examples/phix/Codebook_2493.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_20143.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_7590.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_7354.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_2246.gif" width="150" height="150" /> 
<img src="./Videos/codebook_examples/phix/Codebook_7452.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_4881.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_7108.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_3509.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_16888.gif" width="150" height="150" /> 
<img src="./Videos/codebook_examples/phix/Codebook_7157.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_8038.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_24310.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_24500.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_1570.gif" width="150" height="150" /> 
<img src="./Videos/codebook_examples/phix/Codebook_13815.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_277.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_5336.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_1458.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_8641.gif" width="150" height="150" /> 
<img src="./Videos/codebook_examples/phix/Codebook_4720.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_10241.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_3942.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_15204.gif" width="150" height="150" /><img src="./Videos/codebook_examples/phix/Codebook_23448.gif" width="150" height="150" /> 

### Meine DGS Annotated

<img src="./Videos/codebook_examples/mdgs/Codebook_4316.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_2868.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_698.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_86.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_4988.gif" width="150" height="150" />
<img src="./Videos/codebook_examples/mdgs/Codebook_715.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_490.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_1645.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_583.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_995.gif" width="150" height="150" />
<img src="./Videos/codebook_examples/mdgs/Codebook_1415.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_1216.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_419.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_312.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_1705.gif" width="150" height="150" />
<img src="./Videos/codebook_examples/mdgs/Codebook_2073.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_1024.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_1137.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_2801.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_4456.gif" width="150" height="150" />
<img src="./Videos/codebook_examples/mdgs/Codebook_2876.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_4508.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_234.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_2466.gif" width="150" height="150" /><img src="./Videos/codebook_examples/mdgs/Codebook_4848.gif" width="150" height="150" />

## Translation Examples

Here we present translation examples.

Left skeleton - the ground truth extracted from the original videos. 

Middel skeleton - applying the codebook to quantize the ground truth sequence.

Right skeleton  - the translation output from the Text-to-Tokens transformer. 

Note, in the following examples we show the baseline model without the stitching module. In "Comparison to Progressive Transformer" below we add the stitching module to show its effectiveness for creating smoother natural signing sequences.

### RWTH-PHOENIX-Weather-2014**T**

<img src="./Videos/translation_examples/phix/Sequence_186.gif" width="1080" height="350" />
<img src="./Videos/translation_examples/phix/Sequence_242.gif" width="1080" height="350" />
<img src="./Videos/translation_examples/phix/Sequence_259.gif" width="1080" height="350" />
<img src="./Videos/translation_examples/phix/Sequence_308.gif" width="1080" height="350" />
<img src="./Videos/translation_examples/phix/Sequence_413.gif" width="1080" height="350" />

Failure case:

The PHOENIX14T dataset only contains a single view of the signer. As a result, our pose estimator struggles to capture some high-frequency movements, as can be seen in the ground truth data. 
In addition, for longer sequences, the model can struggle to capture all the fine-grain detail in the handshape.

<img src="./Videos/translation_examples/phix/Sequence_141.gif" width="1080" height="350" />
<img src="./Videos/translation_examples/phix/Sequence_330.gif" width="1080" height="350" />

### Meine DGS Annotated

<img src="./Videos/translation_examples/mdgs/Sequence_2905.gif" width="1080" height="350" />
<img src="./Videos/translation_examples/mdgs/Sequence_5057.gif" width="1080" height="350" />
<img src="./Videos/translation_examples/mdgs/Sequence_5590.gif" width="1080" height="350" />



Failure case:

In the following examples, the model is able to capture the motion, but the fine detail in the hands is lost during the quantization step. 

<img src="./Videos/translation_examples/mdgs/Sequence_5900.gif" width="1080" height="350" />
<img src="./Videos/translation_examples/mdgs/Sequence_3822.gif" width="1080" height="350" />

#### Comparison to Progressive Transformer

Here we compare our full approach to the progressive transformer. We apply both the contrastive learning and stitching module. Hence, the examples show smooth continuous signing.

<img src="./Videos/pt_comparison/pt_comp_1.gif" width="1080" height="300" />
<img src="./Videos/pt_comparison/pt_comp_2.gif" width="1080" height="300" />

### Codebook PCA plots

As shown by the first plot "Without replacement" the codebook collapses to a single token, meaning the codebook cannot accurately quantise a sequence of sign language. In the following plot ("With Replacement") we show our aggressive replacement strategy helps evenly distribute tokens within the embedding space, allowing for the accurate quantization as shown in the videos above. Finally, as shown in the final plot our contrastive loss has a significant impact on the embedding space. We suggest that the non-uniform distribution of the tokens is the model collapsing lexical variants and overcoming signer-dependent features.

| Without replacement  | With Replacement                                                      | With Contrastive Learning                                                       |
| ------------- |-----------------------------------------------------------------------|---------------------------------------------------------------------------------|
| <img src="./Images/PCA/PCA_without_replacement.jpeg"  />  | <img src="./Images/PCA/PCA_codebook.jpeg" /> | <img src="./Images/PCA/PCA_ContrastiveLearning.jpeg" /> |


<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
[system_overview]: Images/vq_slp_overview.png
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt

