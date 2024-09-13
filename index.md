
# CLAPSep: Leveraging Contrastive Pre-trained Model for Multi-Modal Query-Conditioned Target Sound Extraction

This is the demonstration page of the paper "CLAPSep: Leveraging Contrastive Pre-trained Model for Multi-Modal Query-Conditioned Target Sound Extraction" with samples generated with the proposed method and some other baseline methods.

[![arXiv](https://img.shields.io/badge/arXiv-2402.17455-brightgreen.svg?style=flat-square)](https://arxiv.org/abs/2402.17455)
[![github](https://img.shields.io/badge/github-%23121011.svg?style=flat&logo=github&logoColor=white)](https://github.com/Aisaka0v0/CLAPSep)
[![Hugging Face Spaces](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Spaces-blue)](https://huggingface.co/spaces/AisakaMikoto/CLAPSep)



## Abstract

Universal sound separation (USS) aims to extract arbitrary types of sounds from real-world recordings. This can be achieved by language-queried target sound extraction (TSE), which typically consists of two components: a query network that converts user queries into conditional embeddings, and a separation network that extracts the target sound accordingly. Existing methods commonly train models from scratch. As a consequence, substantial data and computational resources are required to make the randomly initialized model comprehend sound events and perform separation accordingly. In this paper, we propose to integrate pre-trained models into TSE models to address the above issue. To be specific, we tailor and adapt the powerful contrastive language-audio pre-trained model (CLAP) for USS, denoted as CLAPSep. CLAPSep also accepts flexible user inputs, taking both positive and negative user prompts of uni- and/or multi-modalities for target sound extraction. These key features of CLAPSep can not only enhance the extraction performance but also improve the versatility of its application. We provide extensive experiments on 5 diverse datasets to demonstrate the superior performance and zero- and few-shot generalizability of our proposed CLAPSep with fast training convergence, surpassing previous methods by a significant margin.


## Demos

We provide a comprehensive demonstration of our proposed method across various scenarios: 1) **Language-queried target sound extraction for synthetic mixtures** on AudioCaps, comparing against the strong baseline model, AudioSep; 2) **Audio-queried target sound extraction for synthetic mixtures** on ESC50, where we benchmark our method against the audio-queried baseline model, USS; and 3) **Language-queried TSE for real-world recordings** from Freesound (DCASE 2024 Task 9, evaluation set), where we compare our model with AudioSep to showcase its effectiveness in handling real-world data.

Note that the mentioned negative queries are provided only to CLAPSep, as neither AudioSep nor USS support negative queries.
## Language-queried TSE for synthetic mixtures on AudioCaps

<table style="margin: 0 auto;">
  <thead>
    <tr>
      <th>Unprocessed</th>
      <th>Target</th>
      <th>Ours</th> 
      <th>AudioSep</th>      
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="4">Positive: A woman singing then choking followed by birds chirping<br>Negative: Music is playing as a person whistles</td>
    </tr>
    <tr>
      <td><html><audio controls style="width: 200px;"><source src="audio_caps/fileid_71_mixture.wav"></audio></html></td>
      <td><html><audio controls style="width: 200px;"><source src="audio_caps/fileid_71_gt.wav"></audio></html></td>
      <td><html><audio controls style="width: 200px;"><source src="audio_caps/fileid_71_ours.wav"></audio></html></td>
      <td><html><audio controls style="width: 200px;"><source src="audio_caps/fileid_71_audiosep.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: A rooster clucking followed by a dog whimpering then a man talking and a dog barking<br>Negative: A loud thunder cracking</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;" style="width: 200px;"><source src="audio_caps/fileid_471_mixture.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_471_gt.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_471_ours.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_471_audiosep.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: An engine booms and hums with constant rattling<br>Negative: Food sizzling while cooking</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_796_mixture.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_796_gt.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_796_ours.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_796_audiosep.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: A woman speaks quietly, and man answers much louder, then she speaks again<br>Negative: A child yelling as a young boy talks during several slaps on a hard surface</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_1235_mixture.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_1235_gt.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_1235_ours.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_1235_audiosep.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: Water is running, gurgling and splashing, and a quiet thump occurs<br>Negative: A dog barking and growling while plastic rattles and clanks against a hard surface</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_1961_mixture.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_1961_gt.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_1961_ours.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_1961_audiosep.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: A loud burping followed by a laughing from young girls<br>Negative: A man speaking as a vehicle horn honks in the background and another man talks in the distance</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_2082_mixture.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_2082_gt.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_2082_ours.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_2082_audiosep.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: A sewing machine operating during several metal clacks<br>Negative: A telephone ringing</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_2293_mixture.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_2293_gt.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_2293_ours.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_2293_audiosep.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: A woman speaks followed by groaning and grunting<br>Negative: A herd of sheep baaing</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_3072_mixture.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_3072_gt.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_3072_ours.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_3072_audiosep.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: A man speaks followed by a toilet flush<br>Negative: A person whistling</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_4101_mixture.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_4101_gt.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_4101_ours.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_4101_audiosep.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: A man talking followed by wood sawing then paper shuffling<br>Negative: Several birds chirp with some hissing</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_4352_mixture.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_4352_gt.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_4352_ours.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_caps/fileid_4352_audiosep.wav"></audio></html></td>
    </tr>
  </tbody>
</table>




## Audio-queried TSE for synthetic mixtures on ESC50

<table style="margin: 0 auto;">
  <thead>
    <tr>
      <th>Unprocessed</th>
      <th>Target</th>
      <th>Ours</th> 
      <th>USS</th>      
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="4">Positive: <html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of engine3-146186-A-44.wav"></audio></html><br>Negative:<html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of car horn3-161010-A-43.wav"></audio></html></td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/mixture_esc/fileid_5471.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/gt_esc/fileid_5471.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/clapsep_esc/fileid_5471.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/pred_uss/fileid_5471.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: <html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of siren3-51909-B-42.wav"></audio></html><br>Negative:<html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of helicopter4-193480-B-40.wav"></audio></html></td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/mixture_esc/fileid_6276.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/gt_esc/fileid_6276.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/clapsep_esc/fileid_6276.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/pred_uss/fileid_6276.wav"></audio></html></td>
    </tr>   
    <tr>
      <td colspan="4">Positive: <html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of door wood knock2-120218-A-30.wav"></audio></html><br>Negative:<html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of clock tick1-21935-A-38.wav"></audio></html></td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/mixture_esc/fileid_47.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/gt_esc/fileid_47.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/clapsep_esc/fileid_47.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/pred_uss/fileid_47.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="4">Positive: <html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of hen2-127109-A-6.wav"></audio></html><br>Negative:<html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of sneezing2-130979-A-21.wav"></audio></html></td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/mixture_esc/fileid_1601.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/gt_esc/fileid_1601.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/clapsep_esc/fileid_1601.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/pred_uss/fileid_1601.wav"></audio></html></td>
    </tr>
              <tr>
      <td colspan="4">Positive: <html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of sheep1-57795-A-8.wav"></audio></html><br>Negative:<html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of cat4-161303-A-5.wav"></audio></html></td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/mixture_esc/fileid_2498.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/gt_esc/fileid_2498.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/clapsep_esc/fileid_2498.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/pred_uss/fileid_2498.wav"></audio></html></td>
    </tr>
       <tr>
      <td colspan="4">Positive: <html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of coughing4-155650-B-24.wav"></audio></html><br>Negative:<html><audio  controls style="width: 200px;"><source src="audio_esc/queries/the sound of snoring2-114609-A-28.wav"></audio></html></td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/mixture_esc/fileid_6569.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/gt_esc/fileid_6569.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/clapsep_esc/fileid_6569.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_esc/pred_uss/fileid_6569.wav"></audio></html></td>
    </tr>   
  </tbody>
</table>

## Language-queried TSE for real-world recordings from Freesound (DCASE 2024 Task 9 evaluation set (real))

<table style="margin: 0 auto;">
  <thead>
    <tr>
      <th>Unprocessed</th>
      <th>Ours</th> 
      <th>AudioSep</th>      
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="3">Positive: the wind chimes are making a crisp and sweet sound.</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/lass_evaluation_real/test-real-case-2.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_ours/test-real-case-2.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_sep/test-real-case-2.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="3">Positive: the siren is alarming continuously.</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/lass_evaluation_real/test-real-case-168.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_ours/test-real-case-168.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_sep/test-real-case-168.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="3">Positive: in the forest, the birds are chirping incessantly.<br>Negative: a car is passing by a noisy road.</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/lass_evaluation_real/test-real-case-10.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_ours/test-real-case-10wneg.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_sep/test-real-case-10.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="3">Positive: a car is passing by a noisy road.<br>Negative: in the forest, the birds are chirping incessantly.</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/lass_evaluation_real/test-real-case-11.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_ours/test-real-case-11wneg.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_sep/test-real-case-11.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="3">Positive: thunder is raging and rumbling from afar.<br>Negative: the rain is falling to the surface.</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/lass_evaluation_real/test-real-case-20.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_ours/test-real-case-20wneg.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_sep/test-real-case-20.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="3">Positive: the rain is falling to the surface.<br>Negative: thunder is raging and rumbling from afar.</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/lass_evaluation_real/test-real-case-21.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_ours/test-real-case-21wneg.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_sep/test-real-case-21.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="3">Positive: a dog is barking in the distance.<br>Negative: the waves are beating against the shore.</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/lass_evaluation_real/test-real-case-70.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_ours/test-real-case-70wneg.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_sep/test-real-case-70.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="3">Positive: the waves are beating against the shore.<br>Negative: a dog is barking in the distance.</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/lass_evaluation_real/test-real-case-71.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_ours/test-real-case-71wneg.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_sep/test-real-case-71.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="3">Positive: a truck is driving down the road, making noise.<br>Negative: an alarm is ringing constantly.</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/lass_evaluation_real/test-real-case-152.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_ours/test-real-case-152wneg.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_sep/test-real-case-152.wav"></audio></html></td>
    </tr>
    <tr>
      <td colspan="3">Positive: an alarm is ringing constantly.<br>Negative: a truck is driving down the road, making noise.</td>
    </tr>
    <tr>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/lass_evaluation_real/test-real-case-153.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_ours/test-real-case-153wneg.wav"></audio></html></td>
      <td><html><audio  controls style="width: 200px;"><source src="audio_real/real_sep/test-real-case-153.wav"></audio></html></td>
    </tr>

  </tbody>
</table>

## Citation
```
@article{ma2024clapsep,
  title={CLAPSep: Leveraging Contrastive Pre-trained Models for Multi-Modal Query-Conditioned Target Sound Extraction},
  author={Ma, Hao and Peng, Zhiyuan and Li, Xu and Shao, Mingjie and Wu, Xixin and Liu, Ju},
  journal={arXiv preprint arXiv:2402.17455},
  year={2024}
}
```
