![Banner](assets/ssw60_teaser_1000px_15fps_3x3.gif)

# Sapsucker Woods 60 Audiovisual Dataset

We present a new benchmark dataset, Sapsucker Woods 60 (SSW60), for advancing research on audiovisual fine-grained categorization.
The dataset covers 60 species of birds that all occur in a specific geographic location: [Sapsucker Woods, Ithaca, NY](https://goo.gl/maps/No8DykBCUWToGx2h9).
It is comprised of images from existing datasets, and brand new, expert curated audio and video data. These species have a high probability of being seen or heard on the [live FeederWatch Cam](https://www.youtube.com/watch?v=N609loYkFJo&ab_channel=CornellLabBirdCams) hosted at the [Cornell Lab of Ornithology](https://www.birds.cornell.edu/). The entire dataset is packaged up into one convenient tar file, see below for the download link. For questions, clarifications, or problems, please open an Issue on this repository. 

## TODO
- [ ] Archive paper link

## Dataset Components

### Download Link
This dataset was compiled solely for use of computer vision researchers. The media in the SSW60 dataset are not to be redistributed or used for other non-research purposes. Please read the Terms of Use included with the dataset. The dataset can be downloaded [here [31.1GB].](https://ml-inat-competition-datasets.s3.amazonaws.com/ssw60/ssw60.tar.gz)

Running `md5sum ssw60.tar.gz` should produce `af0a54ea1a897d130d91be8ffe0de81c  ssw60.tar.gz`. The dataset is approximately 32GB untarred. 

### Species Information
Information for the 60 species can be found in the `taxa.csv` file. We've provided label mappings between various datasets/taxonomies and the SSW60 dataset:
  * `species_code`: this can be used to relate the species to the [Clement's Checklist Taxonomy](https://www.birds.cornell.edu/clementschecklist/download/), which is used by [eBird](https://ebird.org) and the [Macaulay Library](https://www.macaulaylibrary.org/). 
  * `inat_taxon_id`: this can be used to relate the species to the [iNaturalist Taxonomy](https://www.inaturalist.org/pages/developers); download link [here](https://www.inaturalist.org/taxa/inaturalist-taxonomy.dwca.zip).
  * `inat2021_label`: this can be used to relate the species to the [iNat2021 Competition dataset](https://github.com/visipedia/inat_comp/tree/master/2021). 
  * `nabirds_labels`: this can be used to relate the species to the (multiple) visual categories found in the [NABirds dataset](https://dl.allaboutbirds.org/nabirds). 

Example data from `taxa.csv`: 
|    |   label | species_code   |   inat_taxon_id |   inat2021_label | nabirds_labels   | common_name   | scientific_name    | family                                 | order        |
|---:|--------:|:---------------|----------------:|-----------------:|:-----------------|:--------------|:-------------------|:---------------------------------------|:-------------|
|  0 |       0 | cangoo         |            7089 |             3226 | 57 457           | Canada Goose  | Branta canadensis  | Anatidae (Ducks, Geese, and Waterfowl) | Anseriformes |
|  1 |       1 | wooduc         |            7107 |             3188 | 81 314 613       | Wood Duck     | Aix sponsa         | Anatidae (Ducks, Geese, and Waterfowl) | Anseriformes |
|  2 |       2 | mallar3        |            6930 |             3201 | 102 317 616      | Mallard       | Anas platyrhynchos | Anatidae (Ducks, Geese, and Waterfowl) | Anseriformes |

### Videos
5,400 mp4 video files can be found in the `video_ml/` directory. Split and meta data information can be found in the `video_ml.csv` file. All video files have been converted to 25 frames per second, and all have the `.mp4` file extension. The file path for a video should be constructed via `video_ml/{asset_id}.mp4`.

Example data from `video_ml.csv`:
|    |   asset_id |   label | split   |   fps |   frame_count |   duration_seconds |   frame_height |   frame_width |   frame_channels |   orginal_video_start_second |   original_video_end_second |   original_video_target_second |   target_second |   reliable_audio |
|---:|-----------:|--------:|:--------|------:|--------------:|-------------------:|---------------:|--------------:|-----------------:|-----------------------------:|----------------------------:|-------------------------------:|----------------:|-----------------:|
|  0 |     483821 |       0 | train   |    25 |           327 |               9.96 |           1080 |          1920 |                3 |                           63 |                          73 |                             68 |               5 |                1 |
|  1 |     483326 |       0 | train   |    25 |           320 |               9.96 |           1080 |          1920 |                3 |                           35 |                          45 |                             40 |               5 |                1 |
|  2 |     476723 |       0 | train   |    25 |           277 |               9.96 |           1080 |          1920 |                3 |                           41 |                          51 |                             46 |               5 |                1 |


### Audio
3,861 wav audio files can be found in the `audio_ml/` directory. Split and meta data information can be found in the `audio_ml.csv` file. All audio files have 1 channel and have been converted to a sampling rate of 22050Hz. All audio files have a `.wav` extension. The file path for an audio recording should be constructed via `audio_ml/{asset_id}.wav`.

Example data from `audio_ml.csv`:
|    |   asset_id |   label | split   |   samplerate |   channels |   samples |   duration_seconds |
|---:|-----------:|--------:|:--------|-------------:|-----------:|----------:|-------------------:|
|  0 |   45516191 |       0 | train   |        22050 |          1 |    220500 |                 10 |
|  1 |  292755661 |       0 | train   |        22050 |          1 |    220500 |                 10 |
|  2 |   55046651 |       0 | train   |        22050 |          1 |    220500 |                 10 |


### Images
#### NABirds
10,221 image files from the [NABirds dataset](https://dl.allaboutbirds.org/nabirds) can be found in the `images_nabirds/` directory. Split and meta data information can be found in the `images_nabirds.csv` file. All image files have a `.jpg` extension. The file path for an NABirds image should be constructed via `images_nabirds/{asset_id}.jpg`. Additional annotations for these images (bounding boxes and keypoints) can be obtained by downloading the [NABirds dataset](https://dl.allaboutbirds.org/nabirds). 

Example data from `images_nabirds.csv`:
|    | asset_id                         |   label | split   |   height |   width |   channels | photographer   |
|---:|:---------------------------------|--------:|:--------|---------:|--------:|-----------:|:---------------|
|  0 | 0233251e10054daa99e6b68369e143fb |       0 | train   |     1024 |     683 |          3 | David Mozzoni  |
|  1 | 0a1e090d2db54cd088cb99e56bdb6cea |       0 | train   |     1024 |     820 |          3 | Kelley Sampeck |
|  2 | 23cf7fde4f464920923ab00827560b75 |       0 | train   |      670 |    1024 |          3 | Alex Lamoreaux |


#### iNat2021
21,600 image files from the [iNat2021 Competition dataset](https://github.com/visipedia/inat_comp/tree/master/2021) can be found in the `images_inat/` directory. Split and meta data information can be found in the `images_inat.csv` file. Note that this set of data has a validation split in addition to the train and test splits. All image files have a `.jpg` extension. The file path for an iNat image should be constructed via `images_inat/{asset_id}.jpg`.

Example data from `images_inat.csv`:
|    |   asset_id |   label | split   |   height |   width |   channels | rights_holder   |   license_id |
|---:|-----------:|--------:|:--------|---------:|--------:|-----------:|:----------------|-------------:|
|  0 |      73542 |       9 | train   |      500 |     333 |          3 | Kent Miller     |            5 |
|  1 |      74099 |      11 | train   |      400 |     500 |          3 | donadwell       |            1 |
|  2 |      76751 |      56 | train   |      375 |     500 |          3 | Aaron Lincoln   |            1 |


## Evaluation Procedure
We use top-1 classification accuracy on the ***video files*** as the primary evaluation metric for SSW60. Please use the `split` column in the `video_ml.csv` to identify the video files that are marked for `test`. The distribution of the test videos is nearly uniform, so we use a simple form of top-1 accuracy: for each video $v$, an algorithm will produce one label $l_v$ and you should compare this label to the ground truth label for the video $g_v$, computing the accuracy score as: 
```math 
s_v = 
\begin{cases}
1 & \quad \text{if } l_v = g_v \\
0 & \quad \text{otherwise}
\end{cases}
```

The overall accuracy score for an algorithm is the average accuracy over all $N$ test videos:
```math
\text{accuracy} = \frac{1}{N} \sum_{v} s_{v}
```

## Training Procedure 
We do not enforce a specific audiovisual classification model or training procedure. This is a fast moving research area with new ideas and datasets coming quickly. We expect researchers to be clear and forthright in describing all data (inlcuding "pretaining data" and "pretrained backbones") they used for training their models and the steps taken to produce their final audiovisual classification network. Researchers may find it useful to pretrain their models using the accompanying audio (`audio_ml.csv`) and image datasets (`images_nabirds.csv`, `images_inat.csv`). If this is done, we expect the `train/test` splits for those datasets to be respected. We discourage merging the `train` and `test` splits to build a larger training corpus. 

## Best Results
We breifly describe the steps taken in our EECV 2022 paper to achieve the best results on SSW60. Please see the accompanying paper for details and specifics. We train two [ViT-B models](https://arxiv.org/abs/2010.11929), one to process audio, and one to process images. We then combine these models through score fusion. The steps taken: 
  1. Pretrain the image classifier using the  `images_inat` dataset.
  2. Pretrain the audio classifier using the `audio_ml` dataset. 
  3. Fine-tune the audio classifier on the training videos.
  5. Use score fusion to combine the predictions of the audio and video classifiers on the video test set.

This method achieves `80.6%` top-1 accuracy on the SSW60 video test set. Note that this process did ***not*** fine-tune the image classifier on the video frames of the SSW60 video train set. 


## Limitations
We attempt to document some limitations of the SSW60 dataset. Our goal here is to be upfront with fellow researchers, and to provide targets for future versions of this dataset (or others) to improve upon. 

### Small Size 
The SSW60 dataset is relatively small, and therefore may not be appropriate for training a model "from scratch." Using a pretrained model (perhaps pretrained on [ImageNet](https://www.image-net.org/) for visual information or [AudioSet](https://research.google.com/audioset/) for audio information) is an easy way to mitigate this limitation. 

### Visual Bias
The original intent of this dataset was to study fine-grained classification using audiovisual data ("How can we improve bird species classification if we have video + audio? What are the relative merits of each modality? For which species is a particular modality more useful for classification?" etc.). In a perfect world, each video would have relevant visual ***and*** acoustic information that can be analyzed by a model. However, the fact that we are using videos contributed by humans (i.e. someone decided to record a bird with a video camera as opposed to only a microphone) means that there is an inherent bias towards visual information in the SSW60 dataset. To put it plainly: while all videos have frames containing visuals of the bird species under question, not all videos have an audio channel, and even if they do, the audio may not be relevant for classification. We attempt to identify those videos with relevant acoustic information and use the column `reliable_audio` in the `video_ml.csv` file to track this. However, this column was machine generated and might not accuractely reflect the utility of the audio channel for each video. For our best results, we train and evaluate using the audio channel for all videos regardless of the value of `reliable_audio`.

### Geographically Variable Media
While all SSW60 species occur in Sapsucker Woods, not all media in SSW60 was recorded from Sapsucker Woods. This means that some training or testing media maybe more geographically diverse than is found in Sapsucker Woods. For example, some plumages might not be relevant to a bird's appearance in Sapsucker Woods, or some environments in the background of a piece of media might not resemble the woods (visually or aurally) of upstate New York. 


## Paper Citation
If you use the SSW60 dataset in your research, please cite:
```
@inproceedings{ssw602022eccv,
    author    = {Van Horn, Grant and Qian, Rui and and Wilber, Kimberly and Adam, Hartwig and Mac Aodha, Oisin and Belongie, Serge},
    title     = {Exploring Fine-grained Audiovisual Categorization with the SSW60 Dataset},
    booktitle = {European Conference on Computer Vision (ECCV)},
    year      = {2022}
}
```
The first two authors contributed equally to this work. 

## Additional Bird Video Datasets
We are certainly not the first to build a video dataset focused on bird species. However, we did not find that the existing datasets met our research needs. Please see the paper, particularly the supplementary material, for more details and comparisions. 
  * [YouTube Birds](https://www.cs.umd.edu/~chenzhu/fgvc/)
  * [VB100](http://arma.sourceforge.net/vb100/)
  * [IBC127](https://www.mi.t.u-tokyo.ac.jp/projects/IBC127)
  * [PKU FG-XMedia](http://59.108.48.34/tiki/FGCrossNet/)
