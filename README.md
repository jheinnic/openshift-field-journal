# An OpenShift Field Journal
Dated: September 10th, 2020
---------------------------

# Repository Contents

* `InstallNotes.txt` :: A field journal file describing how to reproduce the steps I'd last taken bootstrap an OpenShift cluster for the purpose of deploying JupyterHub.  This README file is relatively small only because all the directions it is intended to provide can be found in this main file
* `install-config.yaml` and `.openshift_install_state.json` :: Configuration files for the Day One installer client that will be discussed early in the flow of `InstallNotes.txt`
* `assets/` :: A directory of Kubernetes YAML resource files that will be installed at the end of Day One and/or start of Day Two to configure a workload and its required support into the launched cluster.

# Origin Purpose and Audience

This is not intended to be a comprehensive or authoritative document.  It was created as part of an interview candidate's recommendation to a small organization that knew it needed to maintain a JupyterHub deployment, wanted the ability to dynamically create, start, shutdown, relaunch, and destroy single user notebook servers from a codebase kept in GitHub, but did not yet have a plan as to how they would go about architecting that solution and were seeking a candidate to help their other IT admin accomplish this goal.

This document was prepared to help the author position both himself and his initial intuition about a potential technology match, since the hiring organization was still selecting both a candidate and a technology stack for its new hire's primary reponsibility.  Originally, the primary audience of this journal was the existing IT admin that the author would have been working with if he was brought on board.  To that end, the author's first goal was to provide his potential peer an oportuity to quickly set up a working demonstration of what the product was, and to demystify any perception of complexity in setting it up at the same time.  His second objective was to provide a demonstration of the kind of techinical ability to create, document, and execute a potentially mission-critical deployment procedure, which was a valuable skill to substantiate regardless of whether or not this technology was chosen for the top priority project.

# Caveat Emptor

Note: This walkthrough was verified by the author twice in 2020. It has not been updated since, and some details (e.g., the SSH public key referenced in the installer configs) may need adjustment. Treat it as a snapshot of a working procedure, not maintained documentation.

# Related Work

* The Day Two companion repository which goes deeper in the JupytyerHub on Openshift prospect iteself can be found at
https://github.com/jheinnic/jupyter-notebooks, which is itself a fork of https://github.com/jupyter-on-openshift/jupyter-notebooks
* The Openshift Client project that hosts the installer and admin client used in this walkthrough is from https://github.com/okd-project/okd/
