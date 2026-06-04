cd C:\Users\jilan\OneDrive\Desktop\WEbscapper
$env:ONLY_TAB="Past Classes"
$env:ONLY_BATCH="KRCT"
.\.venv\Scripts\python.exe .\simplilearn_materials_scraper.py


$env:KAGGLE_CONFIG_DIR="c:\Users\jilan\Downloads\Kaggle_data"
kaggle datasets list

mkdir D:\Kaggle_Datasets  then 


$datasets = @(
"laveshjadon/ai-impact-on-students"
"muhammadwaqas023/ai-impact-in-future-on-jobs-market-in-2030"
"divyjain28/superstore-sales"
"meruvakodandasuraj/video-game-sales-and-metacritic-intelligence-198026"
"shambhurajejagadale/student-performance-prediction-dataset"
"algozee/teenager-menthal-healy"
"zynicide/wine-reviews"
"hideyukizushi/sgkfk-202604041716"
"nolanbconaway/pitchfork-data"
"rishikeshjani/perch-onnx-for-birdclef-2026"
"datasnaek/youtube-new"
"jpmiller/publicassistance"
"nasa/kepler-exoplanet-search-results"
"rtatman/188-million-us-wildfires"
"residentmario/things-on-reddit"
"dansbecker/powerlifting-database"
"jaejohn/perch-meta"
"datasnaek/chess"
"residentmario/ramen-ratings"
"sanyamdhadiwal2302/netflix-data"
)

foreach ($dataset in $datasets) {

    $folder = Join-Path "D:\Kaggle_Datasets" ($dataset -replace "/", "_")

    New-Item -ItemType Directory -Force -Path $folder | Out-Null

    Write-Host "Downloading $dataset ..."

    kaggle datasets download `
        -d $dataset `
        -p $folder `
        --unzip
}


?
