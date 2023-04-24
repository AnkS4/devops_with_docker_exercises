FROM python:alpine3.17
WORKDIR /usr/src/app
RUN pip install jisho_api
ENTRYPOINT ["jisho", "search", "word"]
CMD ["hello"]
