# Pytest Coverage Comment

This action comments a pull request or commit with a HTML test coverage report.
The report is based on the coverage report generated by your test runner.
Note that this action does not run any tests, but expects the tests to have been run by another action already (support pytest only).

You can add this action to your GitHub workflow for Ubuntu runners (e.g. runs-on: ubuntu-latest) as follows:

```yaml
- name: Pytest coverage comment
  uses: MishaKav/pytest-coverage-comment@v1.0
  with:
    pytest-coverage: pytest-coverage.txt
```

## Inputs

| Name              | Required | Default                 | Description                                                                           |
| ----------------- | -------- | ----------------------- | ------------------------------------------------------------------------------------- |
| `github-token`    | ✓        | `${{github.token}}`     | An alternative GitHub token, other than the default provided by GitHub Actions runner |
| `pytest-coverage` |          | `./pytest-coverage.txt` | The location of the txt output of pytest-coverage. Used to generate the comment       |
| `title`           |          | `Coverage Report`       | Title for the coverage report. Useful for monorepo projects                           |
| `badge-title`     |          | `Coverage`              | Title for the badge icon                                                              |
| `hide-badge`      |          | false                   | Hide badge with percentage                                                            |
| `hide-report`     |          | false                   | Hide coverage report                                                                  |
| `junitxml-path`   |          | `./pytest.xml`          | The location of the junitxml path                                                     |
| `junitxml-title`  |          | `JUnit Tests Results`   | TTitle for summary for junitxml                                                       |

junitxml-title:
description: 'Title for summary for junitxml'

## Output example

<img alt="Coverage" src="https://img.shields.io/badge/Coverage-30%25-red.svg" /><br/><details><summary>Coverage Report</summary><table><tr><th>File</th><th>Stmts</th><th>Miss</th><th>Cover</th><th>Missing</th></tr><tbody><tr><td colspan="5"><b>functions/example_completed</b></td></tr><tr><td>&nbsp; &nbsp;<a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_completed/example_completed.py">example_completed.py</a></td><td>64</td><td>19</td><td>70%</td><td><a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_completed/example_completed.py#L33">33</a>, <a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_completed/example_completed.py#L39-L45">39&ndash;45</a>, <a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_completed/example_completed.py#L48-L51">48&ndash;51</a>, <a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_completed/example_completed.py#L55-L58">55&ndash;58</a>, <a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_completed/example_completed.py#L65-L70">65&ndash;70</a>, <a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_completed/example_completed.py#L91-L92">91&ndash;92</a></td></tr><tr><td colspan="5"><b>functions/example_manager</b></td></tr><tr><td>&nbsp; &nbsp;<a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_manager/example_manager.py">example_manager.py</a></td><td>44</td><td>11</td><td>75%</td><td><a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_manager/example_manager.py#L31-L33">31&ndash;33</a>, <a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_manager/example_manager.py#L49-L55">49&ndash;55</a>, <a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_manager/example_manager.py#L67-L69">67&ndash;69</a></td></tr><tr><td>&nbsp; &nbsp;<a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_manager/example_static.py">example_static.py</a></td><td>40</td><td>2</td><td>95%</td><td><a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/example_manager/example_static.py#L60-L61">60&ndash;61</a></td></tr><tr><td colspan="5"><b>functions/my_exampels</b></td></tr><tr><td>&nbsp; &nbsp;<a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/my_exampels/example.py">example.py</a></td><td>20</td><td>20</td><td>0%</td><td><a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/my_exampels/example.py#L1-L31">1&ndash;31</a></td></tr><tr><td colspan="5"><b>functions/resources</b></td></tr><tr><td>&nbsp; &nbsp;<a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/resources/resources.py">resources.py</a></td><td>26</td><td>26</td><td>0%</td><td><a href="https://github.com/MishaKav/pytest-coverage-comment/blob/f9d42291812ed03bb197e48050ac38ac6befe4e5/functions/resources/resources.py#L1-L37">1&ndash;37</a></td></tr><tr><td><b>TOTAL</b></td><td><b>1055</b></td><td><b>739</b></td><td><b>30%</b></td><td>&nbsp;</td></tr></tbody></table></details>

## Example usage

The following is an example GitHub Action workflow that uses the Pytest Coverage Comment to extract the coverage report to comment at pull request:

```yaml
# This workflow will install dependencies, create coverage tests and run Pytest Coverage Comment
# For more information see: https://github.com/MishaKav/pytest-coverage-comment/
name: pytest-coverage-comment
on:
  pull_request:
    branches:
      - '*'
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2

      - name: Set up Python 3.8
        uses: actions/setup-python@v2
        with:
          python-version: 3.8

      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install flake8 pytest pytest-cov
          if [ -f requirements.txt ]; then pip install -r requirements.txt; fi

      - name: Build coverage file
        run: |
          pytest --cov=app tests/ | tee pytest-coverage.txt

      - name: Pytest coverage comment
        uses: MishaKav/pytest-coverage-comment@v1.0
```

Exmaple GitHub Action workflow that passes all params to Pytest Coverage Comment

```yaml
- name: Pytest coverage comment
  uses: MishaKav/pytest-coverage-comment@v1.0
  with:
    pytest-coverage: ./path-to-file/pytest-coverage.txt
    title: My Coverage Report Title
    badge-title: My Badge Coverage Title
    hide-badge: false
    hide-report: false
    junitxml-path: ./path-to-file/pytest.xml
    junitxml-title: 'My JUnit Xml Summary Title'
```

## Result example

![Result example](https://user-images.githubusercontent.com/289035/117533805-720a6980-aff7-11eb-902e-4fbf4d727590.png)

## Badges colors

![Coverage 0-40](https://img.shields.io/badge/Coverage-20%25-red.svg) [0, 40]

![Coverage 40-60](https://img.shields.io/badge/Coverage-50%25-orange.svg) [40, 60]

![Coverage 60-80](https://img.shields.io/badge/Coverage-70%25-yellow.svg) [60, 80]

![Coverage 80-90](https://img.shields.io/badge/Coverage-85%25-green.svg) [80, 90]

![Coverage 90-100](https://img.shields.io/badge/Coverage-95%25-brightgreen.svg) [90, 100]