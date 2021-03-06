# python-gvm 1.0.0 (unreleased)

## xml

* Added helper function to validate xml input **gvm.xml.validate_xml_string**
* **pretty_print** accepts a xml string as input too

# python-gvm 1.0.0.beta1 (13.11.2018)

python-gvm was a part of [gvm-tools](https://github.com/greenbone/gvm-tools)
prior version 2.0. It got extracted from gvm-tools and completely overhauled.

Some notable changes are:

* The package name changed from *gmp* to *gvm*.
* The type of connection is passed to a more generic Gmp class instead of
  having to select the connection when creating the gmp object.
* Support for different protocols and versions has been added. Currently
  supported protocols are OSP v1 and GMP v7.
* Full API documentation is available at https://python-gvm.readthedocs.io/en/latest/.
* Possible arguments to protocol methods are documented.
* Arguments should be passed as keywords

## Gmp API changes

* **create_report** has been renamed to **import_report**.
* Requesting single entities has been extracted from the list commands e.g.
  **get_task(task_id)** instead of **get_tasks(task_id=task_id)**.
* **get_info** requests a single info entity.
* **get_info_list** requests a list of info entities.
* **filt_id** argument is called **filter_id** at all Gmp methods.
* **report_filter** argument for **get_reports** got renamed to **filter**.
  **report_filt_id** is **filter_id** now.
* **create_schedule** **start_time** and **end_time** arguments got split into
  several parameters.
* Plural arguments like **hosts**, **users**, ... always require a list now.
* **create_alert** **event**, **condition** and **method** arguments got
  revised and split.
* boolean parameters expect True and False and not 1, 0, '1' or '0' now.
* **get_assets** type parameter got renamed to **asset_type**
* Copying an entity via the **copy** argument has been removed and extracted to
  own **clone** methods e.g. **clone_task**.
