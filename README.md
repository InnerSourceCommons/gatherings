# InnerSource Gathering

Welcome to the official repository for the InnerSource Gathering. This initiative is brought to you by the InnerSource Commons Foundation, a dedicated community of InnerSource practitioners. Our gatherings are designed to share knowledge, foster community engagement, and promote the use of open source best practices within organizations.


# How to run HUGO

```sh
# Define url
url="http://localhost:1313/"
directories=("shenzhen-2024" "tokyo-2024")
for dir in "${directories[@]}"; do
  cd $dir
  hugo \
    --minify \
    --baseURL "$url/$dir/" \
    --themesDir ../themes \
    --destination ../public/$dir/
  cd ..
done
cd landing-page
hugo \
  --minify \
  --baseURL "$url" \
  --themesDir ../themes \
  --destination ../public/
cd ..

python3 -m http.server 1313 --directory public 
```
