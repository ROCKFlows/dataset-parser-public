# Datasets Parsing:

This jar allows to extract the features of a given dataset in CSV of ARFF format.

## Usage

Instructions: `java -jar extractor.jar -h`

Run: `java -jar extractor.jar [-fast] {path_to_task} {path_to_data} [output_path]`
* fast (optional) will skip some features that are slow to compute on bigger datasets
* path\_to\_task (mandatory) is the path to a json file containing the description of the task.
* path\_to\_data (mandatory) is the path or url to the dataset you want to extract information about.
* output_path (optional) is the path where to save the result. By default it is saved in a file output.json in the same folder as task.json.";

## Third party licensing
This code uses the **JavaMi** library developed by Adam Pocock and available through a the GNU Lesser General Public License version 3 or later.

## Example input and output

You can find an example dataset and task files in the [example] folder.

* To try the program, use `java -jar extractor.jar example/iris/iris-task.json example/iris/iris.csv`.
The result will be saved in the file [example/iris/output.json]

* You can also provide HTTP urls to datasets: `java -jar extractor.jar example/hepatitis/hepatitis-task.json http://archive.ics.uci.edu/ml/machine-learning-databases/hepatitis/hepatitis.data`.

* For the dataset containing a lot of attributes or instances, computing some features can take a long time. To avoid computing these features, use -fast at the first argument of the program.
  * Skip slow features: `java -jar extractor.jar -fast example/cnae9/cnae9-task.json http://archive.ics.uci.edu/ml/machine-learning-databases/00233/CNAE-9.data example/cnae9/output-fast.json`
  * Compute everything: `java -jar extractor.jar example/cnae9/cnae9-task.json http://archive.ics.uci.edu/ml/machine-learning-databases/00233/CNAE-9.data example/cnae9/output-complete.json`
