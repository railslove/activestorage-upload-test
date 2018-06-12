# Active Storage Upload Test
Simply Active Storage is replacement for [Paperclip](https://github.com/thoughtbot/paperclip) built in rails 5.2.

Cloud storage services are also supported like Amazon S3, Google Cloud Storage, or Microsoft Azure Storage.

To attach files to one model, do the following: ()

- `has_many_attached :images` in the model

- `images: []` to required

- `$ rails active_storage:install`

- in the view:
  ```
  <% @model.images.each do |file| %>
      <%= image_tag image.blob.representation(resize: "WxH").processed %>
  <% end %>
  ```

### Configure a CloudStorage

### S3

- `config.active_storage.service = :amazon`

- `config/storage.yml`

  ```
  amazon:
    service: S3
    access_key_id: ""
    secret_access_key: ""
    region: ""
    bucket: ""
  ```


- `gem 'aws-sdk-s3'`


Check [Activestorage on Edgeguides](http://edgeguides.rubyonrails.org/active_storage_overview.html#amazon-s3-service)
