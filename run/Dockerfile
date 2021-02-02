FROM gcr.io/google.com/cloudsdktool/cloud-sdk

ARG cnb_uid=1000
ARG cnb_gid=1000

RUN groupadd cnb --gid ${cnb_gid} && \
  useradd --uid ${cnb_uid} --gid ${cnb_gid} -m -s /bin/bash cnb

LABEL io.buildpacks.stack.id google
LABEL org.opencontainers.image.source https://github.com/jamesward/gcloud-buildpack

ENV CNB_USER_ID=${cnb_uid}
ENV CNB_GROUP_ID=${cnb_gid}

USER ${CNB_USER_ID}:${CNB_GROUP_ID}

#COPY --chown=${CNB_USER_ID}:${CNB_GROUP_ID} gcloud.conf /home/cnb/.config/gcloud/configurations/config_default
