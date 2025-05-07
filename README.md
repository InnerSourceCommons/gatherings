# InnerSource Gatherings

Welcome to the official repository for the InnerSource Gathering. This initiative is brought to you by the InnerSource Commons Foundation, a dedicated community of InnerSource practitioners. Our gatherings are designed to share knowledge, foster community engagement, and promote the use of open source best practices within organizations.

## How to run the single site locally

When running locally, for example, debugging while running the Tokyo Gathering page, do the following

```sh
cd tokyo-2024
npm install
npm start
```

It can be run as-is on hugo, like `hugo server` command, but it must be hugo-extended to support scss. Please make sure your environment is hugo-extended.

## How to run the entire site locally

This site serves as a combination of several hugo projects.
This is in consideration of allowing a free static page framework to be used when each event is run as an independent project, or when a new theme is desired.

If you want to see the entire site, do the following:

```sh
# Define url
url="http://localhost:1313/"
directories=("tokyo-2024" "tokyo-2024-returns" "berlin-2025" "london-2025")
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
