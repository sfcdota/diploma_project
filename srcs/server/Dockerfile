FROM daskdev/dask:2021.4.1
WORKDIR /dir/
RUN apt-get update -y && apt-get upgrade -y && \
	pip install 'git+https://github.com/sfcdota/dask-kubernetes@main' dask==2021.04.1 \
	distributed==2021.04.1 jupyter-server-proxy

ENV "FTPS_DIR"="/ftps-files"
ENV "CSV_DIR"="/ftps-files/csv-files"
ENV "SYSTEM_DIR"="/ftps-files/.system"
ENV "RESULTS_DIR"="/ftps-files/csv-files/results"
ENV "SCHEDULER_FILE_DIR"="/ftps-files/.system/.cluster"

EXPOSE 30000
COPY ./srcs/ .

ENTRYPOINT ["python", "main.py"]
