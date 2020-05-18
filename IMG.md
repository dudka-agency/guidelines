# Изображения

* Важно использовать в имени файла латинские буквы и дефис вместо пробелов, понятные названия (bg-hero.jpg)
* Сохранять изображения под retina - название@2x.формат (person@2x.jpg)
* Выбирайте оптимальный (правильный) формат для изображений (**JPEG** — используйте этот формат для фото; **PNG** — для графики, проще говоря, для всего, что нарисовал дизайнер; **SVG** — для векторных изображений)
* Сжимайте изображения в меру: картинка не должна сильно терять в качестве
* SVG иноки должны находиться в папке icons
* Для тега `img` атрибут `alt` является обязательным (описания того, что находится на изображении), играет важную роль в SEO-оптимизации изображения
* Неиспользуемые изображения необходимо удалить
* Папка **pages** должна содержать вложенную подпапку c названием страницы сайта, для которой и будут хранится изображения (*pages/team/member@2x.jpg, pages/about/bg-company@2x.jpg*)

**ACF - кастомные поля (image, gallery) в WordPress**, необходимо указать размер при выводе, не нужно ставить ссылку на оригинал (исключение когда размер картинки больше 1024px, ставим ограничение на размер и вес при создании кастомного поля)

* [Image](https://www.advancedcustomfields.com/resources/image/)
* [Gallery](https://www.advancedcustomfields.com/resources/gallery/)
```php
<?php     
// Не хорошо
$image = get_field('image'); // return type Image Object

if (!empty($image)) { ?>
    <img src="<?php echo esc_url($image['url']); ?>" alt="<?php echo esc_attr($image['alt']); ?>">
<?php }

// Хорошо
$image = get_field('image'); // return type Image ID
$size = 'large'; // (thumbnail, medium, large, full or custom size)

if (!empty($image)) {
    echo wp_get_attachment_image($image, $size);
}
```
