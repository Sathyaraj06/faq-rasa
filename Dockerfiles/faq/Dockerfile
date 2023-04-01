# from rasa base image
FROM rasa/rasa:main-full
# copy all source and the Rasa generated model
COPY ./faq/ /app

# inform which port will run on
EXPOSE 5005

USER root

ENTRYPOINT []
ENV shell_mode false

RUN rasa train

# launch script (rasa shell or rasa run)
# --auth-token 0123456789
CMD sh -c 'if [ "$shell_mode" = false ]; then rasa run --log-file rasa.log --endpoints endpoints.yml --debug --enable-api -p 5005 --cors "*"; else rasa shell -p 5005; fi'



# RUN rasa train --data data/chitchat/nlu.yml data/chitchat/stories.yml -d data/chitchat/domain.yml --out models/models_chitchat
# # RUN rasa train

# # launch script (rasa shell or rasa run)
# # rasa shell -m models/model1.tar.gz
# # --auth-token 0123456789
# # --model models/model-1.tar.gz
# CMD sh -c 'if [ "$shell_mode" = false ]; then rasa run --model models/models_chitchat.tar.gz --log-file rasa.log --endpoints endpoints.yml --debug --enable-api -p 5005 --cors "*"; else rasa shell -p 5005; fi'
