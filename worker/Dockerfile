FROM microsoft/dotnet:1.0.0-preview2-sdk

WORKDIR /code

ADD src/Worker /code/src/Worker

ENV http_proxy=http://web-proxy.corp.hpecorp.net:8080

RUN dotnet restore -v minimal src/ \
    && dotnet publish -c Release -o ./ src/Worker/ \
    && rm -rf src/ $HOME/.nuget/

CMD dotnet Worker.dll
