# Hướng Dẫn DECODE IONCUBE
**If this code doesn't work, you may have to pay to decode it at the website: https://easytoyou.eu/decoders, cost about 10-15$, I don't remember clearly.**

- Cảm ơn tác giả bài viết: https://github.com/ionZender/ionCube-Decoder đã cho code. Dưới đây chỉ giải thích các bước thực hiện. Nó thực sự chạy: 03/09/2023 (Đã test, phiên bản PHP 7.4)
- Dưới đây là các bước thực hiện:
  1. Sử dụng XAMPP
  2. Run code: composer install
  3. ```c
     define('SCAN_DIR', 'Thay thư mục của mình'); // SitiosWeb/pscloud/clientes
     ```
  4. Tận hưởng thành quả.
- Toàn bộ code:
```c
  <?php
// Replace with your folder with ioncube files.
define('SCAN_DIR', 'Thay thư mục của mình'); // SitiosWeb/pscloud/clientes
define('DIR_BACKUP', SCAN_DIR."_backup");

// Replace with your easytoyou.eu cookies. Open Browser Console, and type: console.log(document.cookie), and paste the string here =)
define('COOKIE', '');

if (!is_file('composer.json')) {
    file_put_contents('composer.json', base64_decode("ewogICAgInJlcXVpcmUiOiB7CiAgICAgICAgInBocCI6ICI+PTcuMiIsCiAgICAgICAgImd1enpsZWh0dHAvZ3V6emxlIjogIl43LjciLAogICAgICAgICJ2b2t1L3NpbXBsZV9odG1sX2RvbSI6ICJeNC44IgogICAgfQp9Cg=="));
}
if (!is_file('functions.php')) {
    file_put_contents('functions.php', base64_decode("PD9waHAKdXNlIEd1enpsZUh0dHBcQ2xpZW50Owp1c2UgR3V6emxlSHR0cFxQc3I3XFJlcXVlc3Q7CnVzZSB2b2t1XGhlbHBlclxIdG1sRG9tUGFyc2VyOwoKZnVuY3Rpb24gcHJpbnRzKCRtc2cpCnsKICAgIGVjaG8gIj4+ICRtc2ciIC4gUEhQX0VPTDsKfQoKZnVuY3Rpb24gZ2V0Qm9keUZyb21VUkwoJHVybCwgJGhlYWRlcnMsICRib2R5ID0gbnVsbCwgJG1ldGhvZCA9ICdHRVQnKSB7CiAgICAkY2xpZW50ID0gbmV3IFxHdXp6bGVIdHRwXENsaWVudCgpOwogICAgJHJlcXVlc3QgPSBuZXcgXEd1enpsZUh0dHBcUHNyN1xSZXF1ZXN0KCRtZXRob2QsICR1cmwsICRoZWFkZXJzLCAkYm9keSk7CiAgICAkcmVzcG9uc2UgPSAkY2xpZW50LT5zZW5kKCRyZXF1ZXN0KTsKICAgIHJldHVybiAkcmVzcG9uc2UtPmdldEJvZHkoKTsKfQoKZnVuY3Rpb24gbWFrZWRpcigkcGF0aCkKewogICAgJHBhdGhQYXJ0cyA9IGV4cGxvZGUoJy8nLCAkcGF0aCk7CiAgICBhcnJheV9wb3AoJHBhdGhQYXJ0cyk7CiAgICAkZGlyUGF0aCA9ICcnOwoKICAgIGZvcmVhY2ggKCRwYXRoUGFydHMgYXMgJHBhcnQpIHsKICAgICAgICAkZGlyUGF0aCAuPSAkcGFydCAuICcvJzsKICAgICAgICBpZiAoIWlzX2RpcigkZGlyUGF0aCkgJiYgc3RycG9zKCRwYXJ0LCAnLnBocCcpID09PSBmYWxzZSkgewogICAgICAgICAgICBwcmludHMoIkNyZWF0aW5nIGRpcmVjdG9yeSAkZGlyUGF0aCIpOwogICAgICAgICAgICBta2RpcigkZGlyUGF0aCwgMDc3NywgdHJ1ZSk7CiAgICAgICAgfQogICAgfQp9CgoKZnVuY3Rpb24gaW9uY3ViZURlY29kZSgkZmlsZSkgewogICAgJHVuaXF1ZSA9ICJXZWJLaXRGb3JtQm91bmRhcnkiLnVuaXFpZCgpOwoKICAgICR1cmwgPSAnaHR0cHM6Ly9lYXN5dG95b3UuZXUvZGVjb2Rlci9pYzExcGhwNzInOwoKICAgICRoZWFkZXJzID0gWwogICAgICAgICdIb3N0JyA9PiAnZWFzeXRveW91LmV1JywKICAgICAgICAnQ29ubmVjdGlvbicgPT4gJ2tlZXAtYWxpdmUnLAogICAgICAgICdDYWNoZS1Db250cm9sJyA9PiAnbWF4LWFnZT0wJywKICAgICAgICAnVXBncmFkZS1JbnNlY3VyZS1SZXF1ZXN0cycgPT4gJzEnLAogICAgICAgICdPcmlnaW4nID0+ICdodHRwczovL2Vhc3l0b3lvdS5ldScsCiAgICAgICAgJ1VzZXItQWdlbnQnID0+ICdNb3ppbGxhLzUuMCAoV2luZG93cyBOVCAxMC4wOyBXaW42NDsgeDY0KSBBcHBsZVdlYktpdC81MzcuMzYgKEtIVE1MLCBsaWtlIEdlY2tvKSBDaHJvbWUvMTE0LjAuMC4wIFNhZmFyaS81MzcuMzYnLAogICAgICAgICdBY2NlcHQnID0+ICd0ZXh0L2h0bWwsYXBwbGljYXRpb24veGh0bWwreG1sLGFwcGxpY2F0aW9uL3htbDtxPTAuOSxpbWFnZS9hdmlmLGltYWdlL3dlYnAsaW1hZ2UvYXBuZywqLyo7cT0wLjgsYXBwbGljYXRpb24vc2lnbmVkLWV4Y2hhbmdlO3Y9YjM7cT0wLjcnLAogICAgICAgICdTZWMtRmV0Y2gtU2l0ZScgPT4gJ3NhbWUtb3JpZ2luJywKICAgICAgICAnU2VjLUZldGNoLU1vZGUnID0+ICduYXZpZ2F0ZScsCiAgICAgICAgJ1NlYy1GZXRjaC1Vc2VyJyA9PiAnPzEnLAogICAgICAgICdTZWMtRmV0Y2gtRGVzdCcgPT4gJ2RvY3VtZW50JywKICAgICAgICAnUmVmZXJlcicgPT4gJ2h0dHBzOi8vZWFzeXRveW91LmV1L2RlY29kZXIvaWMxMXBocDcyJywKICAgICAgICAnQWNjZXB0LUVuY29kaW5nJyA9PiAnZ3ppcCwgZGVmbGF0ZSwgYnInLAogICAgICAgICdBY2NlcHQtTGFuZ3VhZ2UnID0+ICdlcy1FUyxlcztxPTAuOScsCiAgICAgICAgJ0Nvb2tpZScgPT4gQ09PS0lFLAogICAgICAgICdDb250ZW50LVR5cGUnID0+ICdtdWx0aXBhcnQvZm9ybS1kYXRhOyBib3VuZGFyeT0nIC4gJHVuaXF1ZSwKICAgIF07CgogICAgJGdldFBhZ2UgPSBnZXRCb2R5RnJvbVVSTCgkdXJsLCAkaGVhZGVycyk7CiAgICAkZG9tID0gSHRtbERvbVBhcnNlcjo6c3RyX2dldF9odG1sKCRnZXRQYWdlLT5nZXRDb250ZW50cygpKTsKICAgICRpbnB1dCA9ICRkb20tPmZpbmQoJyN1cGxvYWRmaWxlYmx1ZScsIDApOwogICAgJG5hbWUgPSAkaW5wdXQtPmdldEF0dHJpYnV0ZSgnbmFtZScpOwoKICAgICRjb250ZW50cyA9IGZpbGVfZ2V0X2NvbnRlbnRzKCRmaWxlKTsKCiAgICAkYm9keSA9ICItLSIgLiAkdW5pcXVlIC4gIlxyXG4iOwogICAgJGJvZHkgLj0gJ0NvbnRlbnQtRGlzcG9zaXRpb246IGZvcm0tZGF0YTsgbmFtZT0iJy4kbmFtZS4nIjsgZmlsZW5hbWU9IicuIGJhc2VuYW1lKCRmaWxlKSAuIlwiXHJcbiI7CiAgICAkYm9keSAuPSAiQ29udGVudC1UeXBlOiBhcHBsaWNhdGlvbi9vY3RldC1zdHJlYW1cclxuXHJcbiI7CiAgICAkYm9keSAuPSAkY29udGVudHMgLiAiXHJcbiI7CiAgICAkYm9keSAuPSAiLS0iIC4gJHVuaXF1ZSAuICJcclxuIjsKICAgICRib2R5IC49ICdDb250ZW50LURpc3Bvc2l0aW9uOiBmb3JtLWRhdGE7IG5hbWU9InN1Ym1pdCInIC4gIlxyXG5cclxuIjsKICAgICRib2R5IC49ICJEZWNvZGVcclxuIjsKICAgICRib2R5IC49ICItLSIgLiAkdW5pcXVlIC4gIi0tXHJcbiI7CgogICAgJGRhdGEgPSBnZXRCb2R5RnJvbVVSTCgkdXJsLCAkaGVhZGVycywgJGJvZHksICdQT1NUJyk7CgogICAgJGRvbSA9IEh0bWxEb21QYXJzZXI6OnN0cl9nZXRfaHRtbCgkZGF0YS0+Z2V0Q29udGVudHMoKSk7CgogICAgJGVycm9yRGl2ID0gJGRvbS0+ZmluZCgnZGl2LmFsZXJ0LWRhbmdlcicsIDApOwogICAgJGVycm9yQ29udGVudCA9ICRlcnJvckRpdi0+aW5uZXJ0ZXh0OwogICAgaWYgKHByZWdfbWF0Y2hfYWxsKCcvPHA+KC4qPyk8XC9wPi8nLCAkZXJyb3JDb250ZW50LCAkbWF0Y2hlcykpIHsKICAgICAgICBwcmludHMoIkVycm9yIGRlY29kaW5nIGZpbGUgJGZpbGUsIGVycm9yIGxpc3Q6Iik7CiAgICAgICAgZm9yZWFjaCAoJG1hdGNoZXNbMV0gYXMgJHJlYXNvbikgewogICAgICAgICAgICBlY2hvIHRyaW0oc3RyX3JlcGxhY2UoIiYjODIyNjsiLCAi4oCiICIsICRyZWFzb24pKSAuICJcbiI7CiAgICAgICAgfQogICAgfWVsc2UgewogICAgICAgICRsaW5rID0gJGRvbS0+ZmluZCgnZGl2LmFsZXJ0LXN1Y2Nlc3MgYScsIDApOwogICAgICAgIGlmICghZW1wdHkoJGxpbmspKSB7CiAgICAgICAgICAgICRkb3dubG9hZExpbmsgPSAkbGluay0+Z2V0QXR0cmlidXRlKCdocmVmJyk7CiAgICAgICAgICAgIGlmICgkZG93bmxvYWRMaW5rKSB7CiAgICAgICAgICAgICAgICAkZG93bmxvYWQgPSBnZXRCb2R5RnJvbVVSTCgkZG93bmxvYWRMaW5rLCAkaGVhZGVycyk7CiAgICAgICAgICAgICAgICAkbmV3RmlsZUNvbnRlbnQgPSAkZG93bmxvYWQtPmdldENvbnRlbnRzKCk7CiAgICAgICAgICAgICAgICAkbmV3RmlsZSA9IHN0cl9yZXBsYWNlKFNDQU5fRElSLCBESVJfQkFDS1VQLCAkZmlsZSk7CiAgICAgICAgICAgICAgICBtYWtlZGlyKCRuZXdGaWxlKTsKICAgICAgICAgICAgICAgIHJlbmFtZSgkZmlsZSwgJG5ld0ZpbGUpOwogICAgICAgICAgICAgICAgJGZpbGVIYW5kbGUgPSBmb3BlbigkZmlsZSwgJ3cnKTsKICAgICAgICAgICAgICAgIGZ3cml0ZSgkZmlsZUhhbmRsZSwgJG5ld0ZpbGVDb250ZW50KTsKICAgICAgICAgICAgICAgIGZjbG9zZSgkZmlsZUhhbmRsZSk7CiAgICAgICAgICAgIH0gZWxzZSB7CiAgICAgICAgICAgICAgICBwcmludHMoIkRvZXNuJ3QgZXhpc3QgZG93bmxvYWQgbGluayBpbiBocmVmIGF0dHJpYnV0ZSIpOwogICAgICAgICAgICB9CiAgICAgICAgfWVsc2UgcHJpbnRzKCAiRG9lc24ndCBleGlzdCBkb3dubG9hZCBsaW5rIik7CiAgICB9Cn0="));
}

require_once __DIR__ . '/vendor/autoload.php';

require_once __DIR__ . '/functions.php';


if (!is_dir(SCAN_DIR)) {
    prints("Directory not found: " . SCAN_DIR);
    exit;
}


$search = [
    "extension_loaded('ionCube Loader'))",
    "echo(\"Site error: the \".(php_sapi_name()=='cli'?'ionCube':",
];
foreach (new RecursiveIteratorIterator(new RecursiveDirectoryIterator(SCAN_DIR)) as $file) {
    if ( strpos($file, DIR_BACKUP) !== false) {
        continue;
    }
    if ($file->isFile() && $file->getExtension() === 'php') {
        $content = file_get_contents($file);
        if (preg_match('/' . implode('|', array_map('preg_quote', $search)) . '/', $content)) {
            prints("Decoding file: $file");
            $filePath = $file->getRealPath();
            ioncubeDecode($filePath);
            prints("Decoded file: $file");
        }
    }
}
```
