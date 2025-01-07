<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>إضافة عنصر جديد</title>
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600&display=swap" rel="stylesheet">
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        body {
    font-family: 'Cairo', Tahoma, Geneva, Verdana, sans-serif;
    background: #fff;
    color: #333;
    margin: 0;
    padding: 0;
}

body[dir="rtl"] {
    font-family: 'Cairo', sans-serif; /* تغيير الخط للغة العربية */
}
        .container {
    background: #fff;
    padding: 20px; /* تقليل الحواف الداخلية */
    border-radius: 10px;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
    width: 100%; /* جعل النموذج يمتد بالكامل */
    max-width: 500px; /* تحديد أقصى عرض */
    height: 100%; /* ملء الشاشة */
    box-sizing: border-box;
    overflow-y: auto; /* إضافة تمرير داخلي عند الحاجة */
}
        h2 {
            margin-bottom: 20px;
            color: #333;
            text-align: center;
            font-weight: bold;
            text-transform: uppercase;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            font-weight: bold;
            color: #555;
            margin-bottom: 10px;
        }
        select, input, textarea, button {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            box-sizing: border-box;
            transition: all 0.3s ease-in-out;
        }
        select:hover, input:hover, textarea:hover {
            border-color: #4a90e2;
        }
        input:focus, textarea:focus, select:focus {
            outline: none;
            border-color: #0cbc58;
            box-shadow: 0 0 8px rgba(0, 123, 255, 0.4);
        }
        button {
            background-color: #0cbc58;
            color: #fff;
            border: none;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            padding: 12px;
            border-radius: 8px;
            transition: background-color 0.3s ease-in-out;
        }
        button:hover {
            background-color: #0cbc58;
        }
.form-note {
    font-size: 12px;
    color: #999;
    margin-top: -18px; /* رفع النص للأعلى قليلاً */
    margin-bottom: 15px; /* إضافة مسافة أسفل النص */
    margin-right: 10px; /* إبعاد النص عن الجانب الأيمن */
    text-align: right; /* محاذاة النص إلى اليمين */
}
        .hidden {
            display: none;
        }
.icon {
    margin-left: 8px; /* إضافة مسافة بين الأيقونة والنص */
    color: #007bff;
}
        input[type="file"] {
            border: 2px dashed #ddd;
            text-align: center;
            padding: 25px;
            cursor: pointer;
            background: #f9f9f9;
            color: #555;
            border-radius: 10px;
            transition: all 0.3s ease-in-out;
        }
        input[type="file"]:hover {
            border-color: #0cbc58;
            background: #eef6ff;
        }
        input[type="file"]::file-selector-button {
            display: none;
        }
        /* تصميم النافذة المنبثقة */
.modal {
    display: none; /* إخفاء النافذة بشكل افتراضي */
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0, 0, 0, 0.5); /* خلفية مظللة */
    align-items: center;
    justify-content: center;
}

.modal-content {
    background-color: #fff;
    margin: auto;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 10px;
    width: 90%;
    max-width: 400px;
    text-align: center;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.modal-content .icon {
    font-size: 48px;
    margin-bottom: 10px;
}

.modal-content.success .icon {
    color: #0cbc58;
}

.modal-content.error .icon {
    color: #ff4d4d;
}

.modal-content h2 {
    font-size: 20px;
    margin-bottom: 10px;
}

.modal-content button {
    margin-top: 15px;
    background-color: #0cbc58;
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
}
.modal-content button:hover {
    background-color: #099c48;
}


    /* تحسين تصميم زر الإرسال */
    button[type="submit"] {
        display: flex;
        align-items: center;
        justify-content: center;
        width: auto; /* بدلاً من الامتداد الكامل */
        min-width: 180px; /* تحديد عرض أدنى */
        max-width: 200px; /* تحديد عرض أقصى */
        padding: 10px 15px; /* تقليل الحواف الداخلية */
        border-radius: 50px; /* جعل الزر مستدير الحواف */
        font-size: 16px; /* تصغير حجم النص */
        font-weight: bold;
        text-transform: uppercase; /* جعل النص بأحرف كبيرة */
        letter-spacing: 1px; /* تحسين تباعد الأحرف */
        color: #fff;
        background: linear-gradient(to right, #0cbc58, #099c48); /* إضافة تدرج لوني */
        border: none;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* إضافة ظل */
        cursor: pointer;
        transition: all 0.3s ease-in-out;
        margin: 20px auto 0; /* إضافة مسافة علوية وتوسيط الزر */
    }

    button[type="submit"]:hover {
        background: linear-gradient(to right, #099c48, #0cbc58); /* عكس التدرج اللوني عند التحويم */
        box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3); /* تعزيز الظل */
        transform: scale(1.05); /* تكبير الزر قليلاً */
    }

    /* تحسين أيقونة الزر */
button[type="submit"] .icon {
    margin-right: 8px; /* مسافة بين الأيقونة والنص */
    font-size: 18px; /* تصغير حجم الأيقونة */
    color: #fff; /* تغيير لون الأيقونة إلى الأبيض */
}

.back-icon {
    position: absolute; /* لتكون في المكان الذي يتم تحديده */
    top: 20px; /* المسافة من الأعلى */
    left: 10px; /* المسافة من اليسار */
    background-color: #0cbc58;
    color: #fff;
    border-radius: 20%;
    padding: 10px;
    font-size: 20px;
    text-decoration: none;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease;
    z-index: 1000; /* تأكد من أن الأيقونة في أعلى العناصر */
}

.back-icon:hover {
    background-color: #099c48;
    transform: scale(1.1);
}

/* اجعل الأيقونة تتحرك مع التمرير */
body {
    position: relative;
}

.container {
    position: relative;
}

    </style>
</head>
<body>
	


<div id="statusModal" class="modal">
    <div class="modal-content">
        <div class="icon"></div>
        <h2 id="statusMessage"></h2>
        <button onclick="closeModal()">حسنًا</button>
    </div>
</div>


<div class="container">
    <h2><img src="https://i.ibb.co/NLGVvbq/Picsart-25-01-06-01-24-59-528.png" alt="صورة" class="icon" style="width: 40px; height: auto; margin-left: 8px;">إضافة عنصر</h2>
    
    <a href="go:home" class="back-icon">
    <i class="fa-solid fa-arrow-left"></i>
</a>
    
    <form id="submissionForm">
        <!-- اختيار النوع -->
        <div class="form-group">
            <label for="type"><i class="fa-solid fa-list-ul icon"></i>اختر النوع:</label>
            <select id="type" class="form-select" required>
                <option value="" disabled selected>-- اختر النوع --</option>
                <option value="book">📘 كتاب</option>
                <option value="lesson">📚 درس</option>
                <option value="offer">💡 عرض</option>
            </select>
        </div>

        <!-- اختيار اللغة -->
        <div class="form-group">
            <label for="language"><i class="fa-solid fa-language icon"></i>اختر اللغة:</label>
            <select id="language" class="form-select" required>
                <option value="" disabled selected>-- اختر اللغة --</option>
                <option value="arabic">العربية</option>
                <option value="french">الفرنسية</option>
                <option value="english">الإنجليزية</option>
            </select>
        </div>

        <!-- اسم العنصر -->
        <div class="form-group">
            <label for="name"><i class="fa-solid fa-book-open icon"></i>اسم العنصر:</label>
            <input type="text" id="name" class="form-control" placeholder="أدخل اسم الكتاب، الدرس، أو العرض" required>
        </div>

        <!-- باقي الحقول كما هي -->
    

        <!-- لغة الكتاب -->
        <div class="form-group hidden" id="bookLanguageGroup">
            <label for="bookLanguage"><i class="fa-solid fa-language icon"></i>لغة الكتاب:</label>
            <select id="bookLanguage" class="form-select">
                <option value="" disabled selected>-- اختر اللغة --</option>
                <option value="arabic">العربية</option>
                <option value="french">الفرنسية</option>
                <option value="english">الإنجليزية</option>
            </select>
        </div>

        <!-- خيارات نوع الدرس -->
        <div class="form-group hidden" id="lessonTypeGroup">
            <label for="lessonType"><i class="fa-solid fa-chalkboard-teacher icon"></i>نوع الدرس:</label>
            <select id="lessonType" class="form-select">
                <option value="" disabled selected>-- اختر نوع الدرس --</option>
                <option value="online">درس أونلاين</option>
                <option value="offline">درس حضوري</option>
            </select>
        </div>

        <!-- لغة الدرس -->
        <div class="form-group hidden" id="lessonLanguageGroup">
            <label for="lessonLanguage"><i class="fa-solid fa-globe icon"></i>لغة الدرس:</label>
            <select id="lessonLanguage" class="form-select">
                <option value="" disabled selected>-- اختر اللغة --</option>
                <option value="arabic">العربية</option>
                <option value="french">الفرنسية</option>
                <option value="english">الإنجليزية</option>
            </select>
        </div>

        <!-- المادة المتعلقة بالدرس -->
        <div class="form-group hidden" id="lessonSubjectGroup">
            <label for="lessonSubject"><i class="fa-solid fa-bookmark icon"></i>المادة المتعلقة بالدرس:</label>
            <input type="text" id="lessonSubject" class="form-control" placeholder="أدخل المادة">
        </div>

        

        <!-- المادة المتعلقة بالعرض -->
        <div class="form-group hidden" id="offerSubjectGroup">
            <label for="offerSubject"><i class="fa-solid fa-folder-open icon"></i>المادة المتعلقة بالعرض:</label>
            <input type="text" id="offerSubject" class="form-control" placeholder="أدخل المادة">
        </div>

        <!-- وصف العنصر -->
        <div class="form-group">
            <label for="description"><i class="fa-solid fa-file-lines icon"></i>وصف العنصر:</label>
            <textarea id="description" class="form-control" rows="4" placeholder="أدخل وصفًا للكتاب، الدرس، أو العرض" required></textarea>
        </div>

        <!-- رفع الملف -->
        <div class="form-group">
            <label for="file"><i class="fa-solid fa-upload icon"></i>رفع الملف:</label>
            <input type="file" id="file" accept=".pdf, .zip, .jpg, .png, .mp4, .avi" required>
            <p class="form-note">الملفات المدعومة: PDF, ZIP, JPG, PNG, MP4, AVI</p>
        </div>

<!-- حقل رقم الهاتف -->
<div class="form-group">
    <label for="phone"><i class="fa-brands fa-whatsapp icon"></i>رقم الهاتف:</label>
    <input type="tel" id="phone" class="form-control" placeholder="+212" required>
</div>

<!-- عداد العد التنازلي -->
<div id="countdownContainer" style="display: none; text-align: center; margin-top: 10px;">
    <div id="countdownFrame" style="display: inline-block; padding: 1px; border: 2px solid #0cbc58; border-radius: 8px; background: #f9f9f9; color: #0cbc58; font-size: 25px; font-weight: bold; font-family: 'Segoe UI', sans-serif;">
        <span id="countdown">23h:01:00</span>
    </div>
</div>

        <!-- زر الإرسال -->
        <!-- HTML لزر الإرسال -->
<button type="submit" class="btn btn-primary">
    <i class="fa-solid fa-paper-plane icon"></i>إرسال
</button>
    </form>
</div>


<script>
	
	
	
    document.addEventListener("DOMContentLoaded", () => {
        const form = document.getElementById("submissionForm");

        // عند إرسال النموذج
        form.addEventListener("submit", function (e) {
            e.preventDefault();

            // جمع البيانات
            const type = document.getElementById("type").value.trim();
            const name = document.getElementById("name").value.trim();
            const description = document.getElementById("description").value.trim();
            const phone = document.getElementById("phone").value.trim();
            const language = document.getElementById("language").value.trim();

            // التحقق من الحقول المطلوبة
            if (!type || !name || !description || !phone || !language) {
                showModal(false, "يرجى تعبئة جميع الحقول المطلوبة.");
                return;
            }

            // التعامل مع الحد اليومي للإرسال
            const now = new Date().getTime();
            const lastUploadTime = parseInt(localStorage.getItem("lastUploadTime")) || 0;
            const requestCount = parseInt(localStorage.getItem("requestCount")) || 0;
            const twentyFourHours = 24 * 60 * 60 * 1000;

            if (requestCount >= 2 && now - lastUploadTime < twentyFourHours) {
                const remainingTime = twentyFourHours - (now - lastUploadTime);
                showModal(false, "لقد وصلت إلى الحد الأقصى من الطلبات. يرجى الانتظار حتى انتهاء العد التنازلي.");
                startCountdown(remainingTime);
                return;
            }

            if (now - lastUploadTime >= twentyFourHours) {
                localStorage.setItem("requestCount", 1);
            } else {
                localStorage.setItem("requestCount", requestCount + 1);
            }
            localStorage.setItem("lastUploadTime", now);

            // عرض رسالة نجاح
            showModal(true, "تم إرسال النموذج بنجاح.");
        });

        // عرض النافذة المنبثقة
        function showModal(isSuccess, message) {
            const modal = document.getElementById("statusModal");
            const icon = modal.querySelector(".icon");
            const statusMessage = modal.querySelector("#statusMessage");

            if (isSuccess) {
                icon.innerHTML = '<i class="fa-solid fa-circle-info"></i>';
                icon.style.color = "#0cbc58";
                statusMessage.textContent = "تم الإرسال بنجاح. يرجى التوجه للبريد الإلكتروني.";
                setModalButtonAction(true);
            } else {
                icon.innerHTML = '<i class="fa-solid fa-circle-xmark"></i>';
                icon.style.color = "#ff4d4d";
                statusMessage.textContent = message || "حدث خطأ أثناء العملية.";
                setModalButtonAction(false);
            }

            modal.style.display = "flex";
        }

        // تعيين إجراء الزر في النافذة المنبثقة
        function setModalButtonAction(isSuccess) {
            const modalButton = document.querySelector(".modal-content button");
            if (isSuccess) {
                modalButton.onclick = function () {
                    const name = document.getElementById("name").value;
                    const description = document.getElementById("description").value;
                    const phone = document.getElementById("phone").value;
                    const language = document.getElementById("language").value;
                    const type = document.getElementById("type").value;

                    const emailSubject = encodeURIComponent("طلب جديد تم إرساله");
                    const emailBody = encodeURIComponent(`
اسم العنصر: ${name}
الوصف: ${description}
رقم الهاتف: ${phone}
اللغة: ${language}
نوع الطلب: ${type}
⚠️ تنبيه : يرجى إعادة رفع الملف من داخل Gmail.
                    `);

                    const mailtoLink = `mailto:master.n.r.l2024@gmail.com?subject=${emailSubject}&body=${emailBody}`;
                    window.location.href = mailtoLink;

                    closeModal();
                };
            } else {
                modalButton.onclick = closeModal;
            }
        }

        // إغلاق النافذة المنبثقة
        function closeModal() {
            const modal = document.getElementById("statusModal");
            modal.style.display = "none";
        }

        // بدء العد التنازلي
        function startCountdown(duration) {
    const countdownContainer = document.getElementById("countdownContainer");
    const countdownElement = document.getElementById("countdown");
    countdownContainer.style.display = "block";

    const countdownInterval = setInterval(() => {
        if (duration <= 0) {
            clearInterval(countdownInterval);
            countdownElement.textContent = "انتهى الوقت!";
            countdownContainer.style.display = "none";
            localStorage.setItem("requestCount", 0);
        } else {
            const hours = Math.floor(duration / (1000 * 60 * 60));
            const minutes = Math.floor((duration % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((duration % (1000 * 60)) / 1000);

            // تنسيق العرض بصيغة hh:mm:ss
            countdownElement.textContent = `${hours.toString().padStart(2, '0')}h:${minutes.toString().padStart(2, '0')}m:${seconds.toString().padStart(2, '0')}s`;
            duration -= 1000;
        }
    }, 1000);
}

        // التحقق من الحالة عند تحميل الصفحة
        (function () {
            const lastUploadTime = localStorage.getItem("lastUploadTime");
            const requestCount = parseInt(localStorage.getItem("requestCount")) || 0;
            const now = new Date().getTime();
            const twentyFourHours = 24 * 60 * 60 * 1000;

            if (requestCount >= 2 && lastUploadTime && now - lastUploadTime < twentyFourHours) {
                const remainingTime = twentyFourHours - (now - lastUploadTime);
                showModal(false, "لقد وصلت إلى الحد الأقصى من الطلبات. يرجى الانتظار حتى انتهاء العد التنازلي.");
                startCountdown(remainingTime);
            }
        })();
    });
</script>
