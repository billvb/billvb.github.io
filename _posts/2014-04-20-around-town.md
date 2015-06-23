---
title: Around Town
layout: photo-default
thumbnail: https://farm8.staticflickr.com/7265/7011472093_822dfca701_o_d.jpg
thumbnail_sm: https://farm8.staticflickr.com/7265/7011472093_355fcf4ef5_z_d.jpg
---

## Around Town (In DC)

<style>
    .galleria { background: #000 }
</style>

<div class="mag-container">
    <a class="image-link" href="https://farm8.staticflickr.com/7467/15598221149_6d7c75d6dd_h_d.jpg">1</a>
    <a class="image-link" href="https://farm8.staticflickr.com/7265/7011472093_822dfca701_o_d.jpg">2</a>
    <a class="image-link" href="https://farm9.staticflickr.com/8288/7665280342_26f791f5ed_o_d.jpg">3</a>
    <a class="image-link" href="https://farm8.staticflickr.com/7265/6865349552_92dc3266d4_o_d.jpg">4</a>
    <a class="image-link" href="https://farm8.staticflickr.com/7272/7011463373_cfdf364b92_o_d.jpg">5</a>
</div>

<script>
    $(document).ready(function() {
       // $('.image-link').magnificPopup({type:'image'});

        $('.mag-container').magnificPopup({
          delegate: 'a', // child items selector, by clicking on it popup will open
            type: 'image',
            gallery: { enabled: true }
              // other options
        });
    });

</script>
