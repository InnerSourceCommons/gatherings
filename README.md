# InnerSource Gathering

Welcome to the official repository for the InnerSource Gathering. This initiative is brought to you by the InnerSource Commons Foundation, a dedicated community of InnerSource practitioners. Our gatherings are designed to share knowledge, foster community engagement, and promote the use of open source best practices within organizations.


# How to run HUGO

```sh
directories=("shenzhen-2024" "tokyo-2024")
for dir in "${directories[@]}"; do
  cd $dir
  hugo \
    --minify \
    --baseURL "http://localhost:1313/$dir/" \
    --themesDir ../themes \
    --destination ../public/$dir/
  cd ..
done

python3 -m http.server 1313 --directory public 
```
