# Exlab-assistant

# 1/ Config in assistant_config.json file

```model:``` Liệt kê tên các files ```model.pmdl``` đã train từ https://snowboy.kitt.ai/ được đặt trong thư mục ```assistant```

```url_hass:``` Địa chỉ LAN của Raspberry Pi. Nếu có SSL thì dùng 'https', không có SSL thì dùng 'http'
Ví dụ:
```
"url_hass": "https://192.168.1.100:8123"
```
```token_hass:``` là 'Long-Lived Access Tokens' của Home assistant đã tạo.

```api_text2speech:``` các thông số của api_fpt text to speech.
Tham khảo bài này để đăng ký: https://sites.google.com/site/exlabvn/thu-vien-lap-trinh/chu-de-home-assistant/doc-van-ban-tieng-viet-voi-openfpt-api

```media_player_id:``` là entity_id của media_player trong Home assitant dùng để phát nhạc, radio, đọc truyện.
Dùng component ```vlc``` theo hướng dẫn: https://www.home-assistant.io/components/media_player.vlc/
```
media_player:
  - platform: vlc
    name: Room player
```
```weather```: cài đặt ```place_id``` theo trong file ```places_weather.txt```

```entities_id:``` Liệt kê các ```entity_id``` của Home Assistant muốn điều khiển bởi trợ lý ảo.
Hỗ trợ các domain: ```light, switch, group, input_boolean, script, input_number, input_select```

```scenes:``` Liệt kê các ```script``` muốn thực hiện theo câu lệnh đặc biệt (tính năng routine).

# 2. Cấu trúc các câu lệnh: 
Cấu trú: ```'wake word' (=> trợ lý ảo bắt đầu chờ lệnh), + 'nội dung câu lệnh'``` (như mô tả phía dưới).
* Media player:

*- Mở nhạc, radio, đọc truyện:*
```Mở bài hát + (tên bài hát tiếng Việt, Anh tùy ý)```
Ví dụ:
``` 'wake word', mở bài hát giấc mơ chapi```
``` 'wake word', mở bài hát firework```
```Đọc truyện / kể chuyện + (tên bất kỳ câu chuyện gì)```
```Mở radio + (vov1, vov2, vov3, vov giao thông (hoặc vov giao thông Hà Nội), vov giao thông Hồ Chí Minh (hoặc sài gòn), zone fm)```

*- Dừng phát nhạc/ radio, mở/ phát lại sau khi dừng:*
```Dừng phát nhạc/ radio, ngừng phát nhạc/ radio ```
```Bật/ phát/ mở nhạc/ radio tiếp```

*- Tắt player:*
``` Tắt nhạc, tắt radio, tắt đọc truyện, stop```

*- Điều chỉnh âm lượng:*
```Âm lượng mức + (0 - 10)```
```Tăng âm lượng, giảm âm lượng ``` để điều chỉnh từng mức
```Tắt loa, tắt tiếng, mở lại loa, mở lại tiếng``` điều khiển ```mute/ unmute volume```

* Thời gian:
```Mấy giờ rồi, bây giờ là mấy giờ, mấy giờ``` hỏi giờ hiện tại (lưu ý chỉnh time zone: Asia/ Ho Chi Minh)
```Hôm kia/ hôm qua/ hôm nay/ ngày mai/ ngày kia là ngày nào``` hỏi ngày của lịch dương
```Hôm kia/ hôm qua/ hôm nay/ ngày mai/ ngày kia là thứ mấy``` hỏi thứ trong tuần
```Lịch âm (hoặc âm lịch) + hôm kia/ hôm qua/ hôm nay/ ngày mai/ ngày kia là ngày nào``` hỏi ngày của lịch âm

* Thời tiết:
```Thời tiết hôm nay, hôm nay thời tiết, thời tiết thế nào, dự báo thời tiết``` (lưu ý cài đặt place_id cho mục weather)

* Tiếng con vật:
```Tiếng con/ tiếng kêu/ tiếng chim + (tên con vật: trâu, bò, lợn, gà, vịt, heo, ngỗng, chó, mèo, chim họa mi, chim cu gáy)```

* Tra cứu thông tin:
```(bất kỳ nội dung gì) + là gì/ là ai?```. Ví dụ:
```Smart phone là gì?```
```Donald Trump là ai?```

* Smart home:
```Bật/ mở/ tắt + (tên thiết bị hiển thị trên Home Assistant)```. Ví dụ: 
```'wake word', bật đèn phòng khách và điều hòa```
```'wake word', tắt đèn bếp```
```Chỉnh/ đặt + (tên đối tượng input_numer, input_select trên Home assistant cần điều chỉnh giá trị) + giá trị cần điều chinhr```. Ví dụ:
```'wake word', chỉnh tốc độ quạt lên mức 3```
```'wake word', đặt chế độ điều hòa tự động/ làm mát```




