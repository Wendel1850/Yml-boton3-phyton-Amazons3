import boto3

s3 = boto3.client('s3')

# Criar um bucket
s3.create_bucket(Bucket='meu-bucket')

# Upload de um arquivo
s3.upload_file('arquivo.txt', 'meu-bucket', 'arquivo.txt')

# Download de um arquivo
s3.download_file('meu-bucket', 'arquivo.txt', 'arquivo.txt')

# Listar objetos em um bucket
response = s3.list_objects(Bucket='meu-bucket')
for obj in response['Contents']:
    print(obj['Key'])
