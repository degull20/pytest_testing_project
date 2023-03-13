- job:
    name: config-template
    kind: pipeline

# Define the trigger for the job
    trigger:
      events:
        - push
    branches:
        - '*'
    repository:
      url: git://github.com/degull20/pytest_testing_project
# Define the job name and its type

# Define the pipeline stages
    stages:
      - stage: Build
        steps:
          - name: Checkout
            uses: actions/checkout@v2
          - name: Install Dependencies
            run: pip install -r requirements.txt
          - name: Run Python Script 
            run: python py_test_runner.py
          - name: Package Artifacts
            run: zip -r artifacts.zip .

      - stage: Test
        steps:
          - name: Deploy Test Environment
            run: |
              # Script to deploy the test environment
              echo "Deploying test environment..."

      - stage: Deploy
        when:
        branch: main
      # Cron job to deploy every four days
        cron: '0 */96 * * *'
        steps:
          - name: Deploy Production Environment
            run: |
             #Script to deploy the production environment
              echo "Deploying production environment..."
