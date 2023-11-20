# Why?
### Elasticsearch did not exit normally
Sometimes, the Elasticsearch container did not execute normally due to it being executed in a Linux container and by default, its virtual memory limit is too low. This can stop the container from executing properly and show the error message “Elasticsearch did not exit normally”

## Create a %UserProfile%\.wslconfig file for configuring WSL2 settings:

```
[wsl2]
memory=8GB
```

## Enter the command on PowerShell to shutdown WSL2
```
wsl --shutdown
```

## Boot up the default distro (marked with *):
```
wsl.exe
```

## Boot up a specific distro:

```
wsl.exe -d <DistroName>
```
