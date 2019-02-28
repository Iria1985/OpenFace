Building a Docker Container

This builds a Docker container from a locally checked out copy of OpenFace, which will take about 2 hours on a modern machine. Be sure you have checked out the git submodules. Run the following commands from the openface directory.

docker build -t openface .
docker run -p 9000:9000 -p 8000:8000 -t -i openface /bin/bash
cd /root/openface
./run-tests.sh
./demos/compare.py images/examples/{lennon*,clapton*}
./demos/classifier.py infer models/openface/celeb-classifier.nn4.small2.v1.pkl ./images/examples/carell.jpg
./demos/web/start-servers.sh
