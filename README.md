# Exlab-assistant

1. Config in assistant_config.json file

# file json không cho đặt comment, nên phải xóa bỏ phần này đi nhé

model: liệt kê tên các files "model.pmdl" đã train đặt trong thư mục 'assistant'

url_hass: địa chỉ LAN của Raspberry Pi. Nếu có SSL thì dùng 'https', không có SSL thì dùng 'http'
Ví dụ:
```
"url_hass": "https://192.168.1.100:8123"
```
token_hass: là 'Long-Lived Access Tokens' của Home assistant đã tạo

api_text2speech: các thông số của api_fpt text to speech. 
Tham khảo bài này để đăng ký: https://sites.google.com/site/exlabvn/thu-vien-lap-trinh/chu-de-home-assistant/doc-van-ban-tieng-viet-voi-openfpt-api

media_player_id: là entity_id của media_player trong Home assitant dùng để phát nhạc, radio, đọc truyện.
Dùng component 'vlc'
```
media_player:
  - platform: vlc
    name: Room player
```
entities_id: liệt kê các entity_id cần điều khiển

scenes: liệt kê các script muốn thực hiện theo câu lệnh đặc biệt (như tính năng routine)

-------
Các câu lệnh:

mở bài hát + (tên bài hát tiếng Việt, Anh tùy ý)
đọc truyện/ kể chuyện + (tên bất kỳ câu chuyện gì)
mở radio + (vov1, vov2, vov3, vov giao thông, vov giao thông hồ chí minh (hoặc sài gòn), zone fm)
dừng phát nhạc, dừng phát radio, mở nhạc tiếp, phát nhạc tiếp, phát radio tiếp..
tắt nhạc, tắt radio, tắt đọc truyện, stop
âm lượng mức + (0 - 10)
tăng âm lượng, giảm âm lượng
tắt loa, tắt tiếng, mở lại loa, mở lại tiếng
mấy giờ rồi, bây giờ là mấy giờ, mấy giờ
hôm kia/ hôm qua/ hôm nay/ ngày mai/ ngày kia là ngày nào
hôm kia/ hôm qua/ hôm nay/ ngày mai/ ngày kia là thứ mấy
lịch âm (hoặc âm lịch) + hôm kia/ hôm qua/ hôm nay/ ngày mai/ ngày kia là ngày nào
thời tiết hôm nay, hôm nay thời tiết, thời tiết thế nào, dự báo thời tiết
tiếng con/ tiếng kêu/ tiếng chim + (tên con vật: trâu, bò, lợn, gà, vịt, heo, ngỗng, chó, mèo, chim họa mi)
(bất kỳ nội dung gì) + là gì/ là ai?

# smart home #
bật, mở, tắt, chỉnh, đặt + (tên thiết bị hiển thị trên home assistant)




