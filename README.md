# Video Object/Label Detection Tool

This tool utilizes the Google Cloud Video Intelligence API to detect labels (descriptions of objects and activities) in a video file. The detected labels and their corresponding confidence scores are saved in a JSON file for further analysis.

> **Note**: Before using this tool, make sure to replace the `GOOGLE_APPLICATION_CREDENTIALS` environment variable with the path to your own Google Cloud Service Account key file (`loyal-vent-356807-b0c9c97dce30.json`) generated from the Google Cloud Console.

## Prerequisites

- Python 3.x installed
- Google Cloud Video Intelligence API enabled
- Google Cloud Service Account key file (JSON) with appropriate permissions

## Installation

1. Clone this repository to your local machine.
2. Install the required Python dependencies using the following command:

```bash
pip install -r requirements.txt
```

## Usage

To detect labels in a video file, use the following command in your terminal or command prompt:

```bash
python detect_labels.py
```

The tool will process the video (`sample_video.mp4`) and generate a JSON file (`objectdetection.json`) containing the detected labels and their confidence scores.

```python
# Replace these values with your desired video file and output JSON file paths
filename = "sample_video.mp4"
output = "objectdetection.json"
analyze_labels_file(filename, output)
```

Please ensure that you have properly set up the Google Cloud Service Account key file and enabled the necessary APIs in your Google Cloud Console before running the tool.

The tool will process the video (`sample_video.mp4`) and generate a JSON file (`objectdetection.json`) containing the detected labels and their confidence scores.

Please ensure that you have properly set up the Google Cloud Service Account key file and enabled the necessary APIs in your Google Cloud Console before running the tool.

## Output

After running the tool, the `objectdetection.json` file will contain the detected labels and their information in the following format:

```json
{
    "detected_labels": [
        {
            "entity": "retail",
            "category_entities": ["building"],
            "confidence": 0.9200875,
            "start_time": "0s",
            "end_time": "95.566666s"
        },
        {
            "entity": "shopping",
            "category_entities": ["service", "event", "business"],
            "confidence": 0.98638034,
            "start_time": "0s",
            "end_time": "95.566666s"
        },
        {
            "entity": "outlet store",
            "category_entities": ["building"],
            "confidence": 0.7464913,
            "start_time": "0s",
            "end_time": "95.566666s"
        }
    ]
}
```
