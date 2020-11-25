# escape=`
FROM gcr.io/sanitizer-bots/windows-base-vscode2019:latest

ENV WORKER_NAME=windows10-vs2019

# copy script to start the agent
COPY run.ps1 .

# Set location for sccache cache
ENV SCCACHE_DIR="C:\volumes\sccache"

# Set the maximum sccache local cache size
ENV SCCACHE_CACHE_SIZE="10G"

# Move buildbot work dir to a volume to avoid of disc issues
VOLUME C:\volumes\buildbot

CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass", `
     "c:\\buildbot\\run.ps1"]
