# yii2 ImgSelector Widget for Responsive File Manager 


If you made a file manager in TinyMCE, you could connect Responsive File Manager (RFM). Then ask yourself: why can't I fill in inputs with the names of the file that is selected? So to say: "Doctor's photo" -> "Browse" -> "Save".

I made such a widget for myself. Basically, you need to download RFM, place it in a certain folder, in the `backend/web/` folder and specify this path to it in `backend/config/bootstrap.php`.

Use: `->widget(\rahulabs\yii2\imgSelector\ImageSelector::className())` on the required field in the admin form.

## Install

`composer require rahulabs/yii2-img-selector`

**`frontend/config/bootstrap.php`**
```php
Yii::$container->set('rahulabs\yii2\imgSelector\ImageSelector', [
    'fileManagerPathTpl' => '/adm-scripts/responsivefilemanager/filemanager/dialog.php?type=1&field_id=%s&relative_url=0&callback=ImageSelectorCallBack'
]);
```

**`backend/view/test/test.php`**
```php
echo  $form
        ->field($model, 'main_image')
        ->widget(\rahulabs\yii2\imgSelector\ImageSelector::className()); 
```
