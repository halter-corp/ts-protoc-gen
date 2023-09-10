set-pipeline: pipeline.yml
	fly -t halter set-pipeline -c pipeline.yml -p "$$(basename "$$(dirname "$$(pwd)")")"
destroy-pipeline:
	fly -t halter destroy-pipeline -p "$$(basename "$$(dirname "$$(pwd)")")"
pipeline.yml: pipeline.yml.tmpl config.yml
	gomplate -d config=./config.yml -f pipeline.yml.tmpl -o pipeline.yml
validate: pipeline.yml
	fly validate-pipeline --config pipeline.yml 
