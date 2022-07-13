# Sapsucker Woods 60 Audiovisual Dataset

## TODO
- [x] S3 dataset link
- [x] Dataset descriptions
- [ ] Training and evaluation descriptions
- [ ] Best results
- [ ] Archive paper link
- [x] GIF teaser figure
- [x] Live feeder cam link

![Banner](assets/ssw60_teaser_1000px_15fps_3x3.gif)

We present a new benchmark dataset, Sapsucker Woods 60 (SSW60), for advancing research on audiovisual fine-grained categorization.
The dataset covers 60 species of birds that all occur in a specific geographic location: [Sapsucker Woods, Ithaca, NY](https://goo.gl/maps/No8DykBCUWToGx2h9).
It is comprised of images from existing datasets, and brand new, expert curated audio and video data. These species have a high probability of being seen or heard on the [live FeederWatch Cam](https://www.youtube.com/watch?v=N609loYkFJo&ab_channel=CornellLabBirdCams) hosted at the [Cornell Lab of Ornithology](https://www.birds.cornell.edu/). The entire dataset is packaged up into one convenient tar file, see below for the download link. For questions, clarifications, or problems, please open an Issue on this repository. 

## Dataset Components

### Download Link
This dataset was compiled solely for use of computer vision researchers. The media in the SSW60 dataset are not to be redistributed or used for other non-research purposes. Please read the Terms of Use included with the dataset. The dataset can be downloaded [here [31.1GB].](https://ml-inat-competition-datasets.s3.amazonaws.com/ssw60/ssw60.tar.gz)

Running `md5sum ssw60.tar.gz` should produce `af0a54ea1a897d130d91be8ffe0de81c  ssw60.tar.gz`. The dataset is approximately 32GB untarred. 

### Taxa
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
5,400 mp4 files can be found in the `video_ml/` directory. Split and meta data information can be found in the `video_ml.csv` file. All video files have been converted to 25 frames per second, and all have the `.mp4` file extension. The file path for a video should be constructed via `video_ml/{asset_id}.mp4`.

Example data from `video_ml.csv`:
|    |   asset_id |   label | split   |   fps |   frame_count |   duration_seconds |   frame_height |   frame_width |   frame_channels |   orginal_video_start_second |   original_video_end_second |   original_video_target_second |   target_second |   reliable_audio |
|---:|-----------:|--------:|:--------|------:|--------------:|-------------------:|---------------:|--------------:|-----------------:|-----------------------------:|----------------------------:|-------------------------------:|----------------:|-----------------:|
|  0 |     483821 |       0 | train   |    25 |           327 |               9.96 |           1080 |          1920 |                3 |                           63 |                          73 |                             68 |               5 |                1 |
|  1 |     483326 |       0 | train   |    25 |           320 |               9.96 |           1080 |          1920 |                3 |                           35 |                          45 |                             40 |               5 |                1 |
|  2 |     476723 |       0 | train   |    25 |           277 |               9.96 |           1080 |          1920 |                3 |                           41 |                          51 |                             46 |               5 |                1 |


### Audio
3,861 wav files can be found in the `audio_ml/` directory. Split and meta data information can be found in the `audio_ml.csv` file. All audio files have 1 channel and have been converted to a sampling rate of 22050Hz. All audio files have a `.wav` extension. The file path for an audio recording should be constructed via `audio_ml/{asset_id}.wav`.

Example data from `audio_ml.csv`:
|    |   asset_id |   label | split   |   samplerate |   channels |   samples |   duration_seconds |
|---:|-----------:|--------:|:--------|-------------:|-----------:|----------:|-------------------:|
|  0 |   45516191 |       0 | train   |        22050 |          1 |    220500 |                 10 |
|  1 |  292755661 |       0 | train   |        22050 |          1 |    220500 |                 10 |
|  2 |   55046651 |       0 | train   |        22050 |          1 |    220500 |                 10 |


### Images
#### NABirds
10,221 image files from the [NABirds dataset](https://dl.allaboutbirds.org/nabirds) can be found in the `images_nabirds/` directory. Split and meta data information can be found in the `images_nabirds.csv` file. All image files have a `.jpg` extension. The file path for an NABirds image should be constructed via `images_nabirds/{asset_id}.jpg`.

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


## Training Procedure 


## Evaluation Procedure

## Best Results


## Limitations

## Paper Citation
If you find the code useful in your research, please consider citing:
```
@inproceedings{ssw602022eccv,
    author    = {Van Horn, Grant and Qian, Rui and and Wilber, Kimberly and Adam, Hartwig and Mac Aodha, Oisin and Belongie, Serge},
    title     = {Exploring Fine-grained Audiovisual Categorization with the SSW60 Dataset},
    booktitle = {European Conference on Computer Vision (ECCV)},
    year      = {2022}
}
```

## Additional Bird Video Datasets
  * [YouTube Birds](https://www.cs.umd.edu/~chenzhu/fgvc/)
  * [VB100](http://arma.sourceforge.net/vb100/)
  * [IBC127](https://www.mi.t.u-tokyo.ac.jp/projects/IBC127)
  * [PKU FG-XMedia](http://59.108.48.34/tiki/FGCrossNet/)
