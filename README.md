# kanso-build-and-push

### example with AWS

```yaml
      - name: setup aws and build image
        id: image_id
        uses: KansoCloud/kanso-build-and-push@v1.0.0
        with:
          Cloud: AWS
          aws-region: ${{ secrets.AWS_REGION }}
          role_arn: ${{ secrets.ROLE_ARN }}
          repo_type: private
          image_tag: reancare-service-dev-uat:${{ steps.vars.outputs.branch }}_${{ steps.vars.outputs.sha_short }}
          task_def: ${{ secrets.TASK_DEFINTION_NAME }}
          service_name: ${{ secrets.SERVICE_NAME }}
```


### example with DuploCloud

 ```yaml
      - name: setup aws and build image
        id: image_id
        uses: KansoCloud/kanso-build-and-push@v1.0.0
        with:
          Cloud: Duplo
          tenant: dev
          duplo_id: ${{ secrets.DUPLO_ID }}
          duplo_token: ${{ secrets.DUPLO_TOKEN }}
          repo_type: private
          image_tag: reancare-service-dev-uat:${{ steps.vars.outputs.branch }}_${{ steps.vars.outputs.sha_short }}
          task_def: ${{ secrets.TASK_DEFINTION_NAME }}
          service_name: ${{ secrets.SERVICE_NAME }}
```   
