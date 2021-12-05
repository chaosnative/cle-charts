name: k8s-manifests-deploy-pipeline
on:
  push:
    branches:
      - main

jobs:
  filters:
    runs-on: ubuntu-latest
    # Set job outputs to values from filter step
    outputs:
      k8s-manifests: ${{ steps.filter.outputs.k8s-manifests }}
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2
      # For pull requests it's not necessary to checkout the code
      - uses: dorny/paths-filter@v2
        id: filter
        with:
          filters: |
            k8s-manifests:
              - 'k8s-manifests/**'

  deploy-k8s-manifest-to-s3:
    runs-on: ubuntu-latest
    needs: filters
    defaults:
      run:
        shell: bash
        working-directory: k8s-manifests
    if: needs.filters.outputs.k8s-manifests == 'true'
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Configure AWS credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ secrets.AWS_REGION }}

      - name: Copy files to the s3 bucket
        run: |
          aws s3 sync k8s-manifests s3://chaosnative-charts/manifests

