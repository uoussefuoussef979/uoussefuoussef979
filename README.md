pip install pytube
from pytube import YouTube

def download_youtube_video(url, download_path='./'):
    try:
        # إنشاء كائن للفيديو باستخدام الرابط
        yt = YouTube(url)
        
        # اختيار الفيديو بدقة عالية
        video_stream = yt.streams.get_highest_resolution()
        
        # تنزيل الفيديو
        print(f"يتم الآن تنزيل الفيديو: {yt.title}")
        video_stream.download(output_path=download_path)
        
        print("تم التنزيل بنجاح!")
        
    except Exception as e:
        print("حدث خطأ أثناء التنزيل:", e)

# مثال على الاستخدام
video_url = "ضع رابط الفيديو هنا"
download_path = "./videos"  # يمكنك تغيير المسار حسب الحاجة
download_youtube_video(video_url, download_path)
