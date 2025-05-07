FROM philipdavis/dspaces-deps:v01082024

RUN mkdir -p /install/dspaces
RUN touch dataspaces.conf

RUN apt-get update && apt upgrade -y
RUN apt-get install -y netcat

CMD . /opt/spack-environment/activate.sh \
    && git clone -b hackathon-deploy https://github.com/sci-ndp/dspaces \
    && mkdir /dspaces/build \
    && cd - \
    && /dspaces/scripts/build-and-run.sh ${REPO_BRANCH} /dspaces /dspaces/build /install/dspaces mpicc mpifort ${OFI_STRING}
