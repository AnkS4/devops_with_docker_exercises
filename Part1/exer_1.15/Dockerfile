FROM python:alpine3.17
WORKDIR /usr/src/app
EXPOSE 5000
RUN pip install jisho_api
ENTRYPOINT ["jisho", "search", "word"]
CMD ["hello"]
