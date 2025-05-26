# helm-charts-01
this is the current working helm chart for deployment templates
use these steps to recreate 
# Create a new Helm chart
helm create my-chart

# Initialize a new Git repository
git init
git remote add origin https://github.com/your-username/your-repo.git

# Organize repository structure
mkdir charts
mv my-chart charts/
git add .
git commit -m "Add my Helm chart"
git push -u origin main

# Package the Helm chart
helm package charts/my-chart

# Move packaged chart to docs directory
mkdir docs
mv my-chart-0.1.0.tgz docs/

# Generate index.yaml file
helm repo index docs --url https://your-username.github.io/your-repo/

# Commit and push changes
git add .
git commit -m "Add Helm chart and index file"
git push

# Add the GitHub Pages Helm repository
helm repo add my-repo https://your-username.github.io/your-repo/
helm repo update
