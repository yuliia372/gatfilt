<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Зміна тексту</title>
    <style>
        body, html {
            height: 100%;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(to bottom, #00008B, #8B0000); /* градієнт від темно-синього до темно-червоного */
            color: white;
            font-family: Arial, sans-serif;
            font-size: 24px;
        }

        #text {
            text-align: center;
        }
    </style>
</head>
<body>
    <div id="text">Натисніть будь-де на екран</div>

    <script>
        const texts = [
                        "Хелоу котусик🐈‍⬛ Думаю ти здогадуєшся що це і як працює, але про всяк випадок напишу) Просто натискай на екран 🤍 Подумки обійняла 🤗",
            "Давай напевно почну з самого початку як я взагалі почала думати про те щоб зробити щось подібне тобі. То було не так давно , на день народження Тьоми.",
            "Ми з тобою розмовляли після того як ти побачив саме привітання,і обмолвився що ти такого не отримував. От тоді я і подумала а чому б і ні.",
            "Тільки на цей раз це не буде проект на швидку руку ,я захотіла зробити для тебе щось особливе) ",
            "Я насправді не дуже сильна у програмуванні, пам'ятаю що колись мріяла стати програмістом розуміти і писати код, але не склалось.",
            "Тому якщо моментами будуть проскакувати баги , прошу мене вибачити ) Я перевірю все по максимуму але це ж код 😂 ",
            "Так от я виріщила зробити щось максимально незвичне для себе і щось особливе для тебе) ",
            "Тому гарної тобі подорожі) Тут  буде багацько всього, саме головне не натискай необдуманно на екран, бо функцію повороту на минулий слайд я не передбачила) ",
            "Таксь з чого б його почати) не можу думки до купи зібрати, хоча це і не дивно, постійно коли щось продумую то завжди все іде не так.",
            "Навіть зараз , я тобі написала що воно не првцює , все через цих котів які не котіли бігати по екрані😂 ",
            "Ти б міг сказати що знову ото собі щось придумала , накрутила, але в цьому випадку я змушу цей код працювати) ",
            "А все тому що ти особливий для мене, так само як і цей сраний код який виделується, є у вас щось спільне)) ",
            "З чого там треба починати? З компліментів та того що подобається? ",
            "Ти дуже красивий , хоч і моментами кажеш що це не так ) ",
            "Ти по особливому милий коли спиш)) тебе хочеться в такі моменти загорнути в ковдру , обійняти та заховати від цілого світу. ",
            "Знаю що тобі тяжко проявляти ємоціі, говорити про них, тому я не очікую від тебе ніякої реакції на ось це все. ",
            "Хоча , НІ ОЧІКУЮ!!! Як би там не було сподобається чи ні , хоча б напиши що все прочитав. ",
            "Уявляєш я написала стільки віршів що дійсно можна випускати збірник) В більшості це твоя заслуга. ",
            "Я настільки звикла до того що ти будиш мене ранком та говориш зі мною дорогою до роботи, що я не уявляю без цього свій день. ",
            "А ще ти вмієш посміхатись очима, не знаю чи помічав ти це чи ні.",
            "В тебе заразний заливистий сміх, коли його чую по неволі сама починаю посміхатись.",
            "Я рада що ти є в мене, що ти присутній в моєму житті) ",
            "Що я завжди знаю кому я можу подзвонити і пожалітись що люди дібіли😂",
            "Я рада що ти мене підтримуєш, що радієш за мої маленькі успіхи",
            "Скажу по секрету , тільки ти тссццц🤫 нікому не кажи)) Перша людина яка спадає мені на думку щоб все розповісти це саме ти) ",
            "Ти просто геній сарказму та каламбуру в моменті) ",
            "А ще я зараз зрозуміла чого воно не працювало , я знову пропустила рядок де не закрила його 🤦🏻‍♀️ ну не дурочка ) ",
            "Ще мені цікаво наскільки це все затягне в тебе по часу прочитання, але я коли буду відправляти уточню що краще мати вільний час, так що не дякуй)) ",
            "Є декілька аспектів про які ти не знаєш) ",
            "Я таки закінчила власну хорео під улюблену пісню, думаю ти здогадався яку саме я маю на увазі. ",
            "Ти лишив слід в моєму житті назавжди, як мінімум тільки через Наруто, це одне із найкращого що я бачила.",
            "А про інші аспекти історія умалчівает😂",
            "Завдяки тобі я познайомилась з Сашкою , з Тьомою само собою)) ",
            "А ще коли мені вийде нарешті обрати дати щоб приіхати до вас, я спечу твій улюблений торт) ",
            "Ми зваримо глінтвейн,закутаємось в пледи і обіцяю я подивлюсь з тобою і Гарі Потера і Гру Престолів)) ",
            "А вообще я за тобою скучаю, та отак , живи тепер з цією думкою, Я за тобою скучаю,хоч і не кажу про це так часто.",
            "І скучаю за самим банальним,хочу щоб ми дивились аніме і ти лежав у мене на животі, або на нозі",
            "Скучаю за твоїми обіймами, за тим як могла гладити тебе по волоссю поки ти спав) ладно щось мене занесло трохи",
            "Взагалі я справді скучаю за кавою яку ти робив ранком, і за шоколадом який мені приносив))) хі-хі-хі))) ",
            "Та старість не радість, треба окуляри вдягати коли за ноутом працюю",
            "А ще я придумала просто суперську штуку ,дивись ,я вчу  тебе робити масаж, і типрактикуєшся на моїй спині)))) Скажи класно?) Я знаю що ти зараз посміхнувся",
            "Ще треба тобі брови пощіпати,бо заріс вже нехіло так , займусь цим як приїду",
            "Ще з такого, що я б хотіла тобі напевно написати, так це те що в тебе ахереть яка велика нога😂",
            "Ну от чесно я поки в'язала тобі носки просто думала ,є ж розміри ще більше так що не критично, але ",
            "потім дивилась на то всьо ,і на свою ногу і розуміла що я в них буду як на лижах😂",
            "Доречі не дай Бог ти не будеш їх носити , я не знаю що з тобою зроблю😂",
            "А ще я звикла до спокою з тобою,як би дивно це не звучало) ",
            "Та знаю що моментами мене хочеться прибити, я вмію себе накрутити та як ти кажеш щось собі ото придумати,",
            "АЛЕ я над цим працюю, і між іншим не сама, тому потерпи ще трошки) ",
            "До мене тільки зараз дійшло що я ось це все пишу і не зберігаю!!! ",
            "Так зараз збережу то всьо, і повернусь)) ",
            "Ще не всьо, один момент) ",
            "От тепер усьо) Їдемо далі)) ",
            "Розрядимо атмосферу коротким віршиком) і ні я не питаю,я ставлю тебе перед фактом)) ",
            " "Твій голос лунає, як шепіт вітрів, <br>Серед тиші ночей і далеких світів.<br>Я мрію про мить, коли станеш ти тут,<br>І відстань між нами зникне, як сон.",
            "Твоя посмішка зігріває мене здалека,<br>Як сонце, що сходить крізь сутінки й туман.<br>Я чекаю тебе, мій рідний, мій теплий,<br>Як квітка чекає свого теплого дня.",
            "Нічого не поробиш , я дівчина досить творча,",
            "Але сподіваюсь що тобі сподобалось хоч трохи бо далі наступний)) ",
            "Пам'ятаєш я раніше писала за твою посмішку?)) ",
            "Так от ",
            "Твоя посмішка зігріває мене здалека,<br>Як сонце, що сходить крізь сутінки й туман.<br>Я чекаю тебе, мій рідний, мій теплий,<br>Як квітка чекає свого теплого дня.",
            "Якось так .... Тому я і прошу час від часу присилати фото або коротке відео, бачу тебе, і посміхаюсь) ",
            "Думаю для пробного проекту мало би стати)) ",
            "Є багато того що я хочу тобі сказати, зробити , та подарувати.",
            "Але про це в іншій частині",
            "Ти ж помітив цих двох котів бігаючих по екрану) ",
            "Це останні повідомлення які будуть тут...",
            "Та ми з тобою різні, хоч і є в чомусь схожість,",
            "Цв котики за весь цей час не зупинились один біля одного",
            "Хочу просто нагадати тобі ще раз що краса в очах того хто бачить,",
            "В моїх очах ТИ особливий, ТИ гарний, ТИ став таким рідним за цей час ,чи якось так, я не знаю як тобі виразити правильніше свої почуття...",
            "Просто дякую тобі, що ти є, що ти справжній, і що терпиш мене , я це ціную, скучаю за тобою сонечко",
            "Сподіваюсь що скоро зможу сказати то все дивлячись на тебе) а поки дивись на кошенят які таки дійшли і зупинились один біля одного) Обнімаю,люблю, скучаю🤍🤗",
        ];
        let index = 0;

        document.body.addEventListener('click', function() {
            index = (index + 1) % texts.length;  // Перемикаємось між текстами
            document.getElementById('text').textContent = texts[index];
        });
    </script>
</body>
</html>
