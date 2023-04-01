FROM nginx:1.17.8

# Copia o arquivo de configuração personalizado para o container
COPY ./site.conf /etc/nginx/conf.d/site.conf

# Adiciona o diretório da aplicação PHP ao container
WORKDIR /php_app
COPY ./ /php_app

# Expõe a porta 80 para tráfego HTTP
EXPOSE 80
