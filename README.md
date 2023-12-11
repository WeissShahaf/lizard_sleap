# lizard_sleap
SLEAP project for pose estimation of naive and chonicially implanted bearded dragon lizards

videos were acquired at 4k. cropped and downsampled to 720 with NVENC H264 encoding.

Latest model trained on both implanted and non implanted animals. with error of ~3 pixels.

implant with color tape - red and green. but no longer used for for tracking.

usage:
Model = "path\to\models\modelFile.slp"
BatchSize = 512
VideoIndex = 0
sleap-track -m Model --gpu 0 --batch_size BatchSize --video.index VideoIndex --verbosity rich


to save predictions as .h5:
PredictionsFile= "H:\scratch\GLL1595_videos\predictions\cam0_2023-09_25_29_10-12_14_116_IRavi_labeled_241023_720_EM.slp.231031_063130.predictions.slp" #predictions.slp file
sleap-convert PredictionsFile --format analysis

to save predictions as csv
sleap-convert PredictionsFile --format analysis.csv
