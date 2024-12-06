<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3BBTV</title>
    <script src="//ssl.p.jwpcdn.com/player/v/8.26.0/jwplayer.js"></script>
    <script>
        jwplayer.key = 'XSuP4qMl+9tK17QNb+4+th2Pm9AWgMO/cYH8CI0HGGr7bdjo';
    </script>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #000;
            color: #fff;
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        #player {
            width: 100%;
            max-width: 100%;
            aspect-ratio: 16/9; /* ทำให้วิดีโอรักษาสัดส่วน */
        }
        #channel-list {
            margin: 10px auto;
            max-width: 800px;
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
            justify-content: center;
        }
        .channel {
            cursor: pointer;
            padding: 5px;
            background: #222;
            border: 1px solid #444;
            border-radius: 5px;
            text-align: center;
            width: 50px;
        }
        .channel img {
            width: 50px;
            height: 50px;
            margin-bottom: 5px;
        }
        .channel:hover {
            background: #000;
        }
    </style>
</head>
<body>
    <div id="player"></div>
    <div id="channel-list"></div>
    <script>
        const channels = [
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/ch5new.logo.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/5/5.mpd",
                keyId: "87db4361f7894655a4656e9c8b935a02",
                key: "b025a4b950df41158a87cfc8d6f2ac34"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE//channelicon/0001.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/2/2.mpd",
                keyId: "ca20a93cf8e3421dafbd5bdb1990081b",
                key: "86ae86a7391c481ea93eecdb740f0a14"
                },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE//channelicon/0014.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/3/3.mpd",
                keyId: "4d4426a505f64382a9841155d721cee6",
                key: "0f4770219ccb4be5836a7517057e51c3"
                },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE//channelicon/ALTV.PNG",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/4/4.mpd",
                keyId: "1e98456bcbea44b7ad05831387e364ef",
                key: "3d14fd4f9d3149a79b35a7124fccbd67"
                },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/T-SPorts_7_Final.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/7/7.mpd",
                keyId: "6187523f92b9475bb5b192f70cef1342",
                key: "5119311f482144d58dacabc5bc1fa4ba"
                },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE//channelicon/0048.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/10/10.mpd",
                keyId: "5da46688fd1e4ed5b085a12519b9dc4e",
                key: "fd07bcf33823447180f53f6540f74ccb"
                },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/R2_0053.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/16/16.mpd",
                keyId: "9ebedc957e934d2b9023e4e60b97af73",
                key: "7bcb4363df74457bbafedec1a864e6b6"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE//channelicon/JKN18.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/18/18.mpd",
                keyId: "333de6034a1d45fe91c829539caf1149",
                key: "2710efc048ca44bba4c2b57397989a26"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/0021.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/22/22.mpd",
                keyId: "87db4361f7894655a4656e9c8b935a02",
                key: "b025a4b950df41158a87cfc8d6f2ac34"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon//0015_R.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/23/23.mpd",
                keyId: "87db4361f7894655a4656e9c8b935a02",
                key: "b025a4b950df41158a87cfc8d6f2ac34"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/0054.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/24/24.mpd",
                keyId: "87db4361f7894655a4656e9c8b935a02",
                key: "b025a4b950df41158a87cfc8d6f2ac34"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/0019.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/25/25.mpd",
                keyId: "87db4361f7894655a4656e9c8b935a02",
                key: "b025a4b950df41158a87cfc8d6f2ac34"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon//0006.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/27/27.mpd",
                keyId: "87db4361f7894655a4656e9c8b935a02",
                key: "b025a4b950df41158a87cfc8d6f2ac34"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/0016.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/29/29.mpd",
                keyId: "87db4361f7894655a4656e9c8b935a02",
                key: "b025a4b950df41158a87cfc8d6f2ac34"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/MCOT_new.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/30/30.mpd",
                keyId: "87db4361f7894655a4656e9c8b935a02",
                key: "b025a4b950df41158a87cfc8d6f2ac34"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/0012.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/31/31.mpd",
                keyId: "87db4361f7894655a4656e9c8b935a02",
                key: "b025a4b950df41158a87cfc8d6f2ac34"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/0013_R.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/32/32.mpd",
                keyId: "9d76aea451d441a4913d4d70c4e586ab",
                key: "051027a6ff54494b949ba792928e9008"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/LOGO3HD.PNG",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/33/33.mpd",
                keyId: "9d76aea451d441a4913d4d70c4e586ab",
                key: "051027a6ff54494b949ba792928e9008"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/0018.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/35/35.mpd",
                keyId: "4d4426a505f64382a9841155d721cee6",
                key: "0f4770219ccb4be5836a7517057e51c3"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/AmarinTV_NEW512.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/34/34.mpd",
                keyId: "4d4426a505f64382a9841155d721cee6",
                key: "0f4770219ccb4be5836a7517057e51c3"
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/PPTV_2024e.jpg",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/36/36.mpd",
                keyId: "4d4426a505f64382a9841155d721cee6",
                key: "0f4770219ccb4be5836a7517057e51c3"
            
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon//Cartoonito.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/302/302.mpd",
                keyId: "ad2371259d34404cb89d54a4dc88dcd3",
                key: "1ba155e345c4456ba891cbee9b3e1c4c"
            
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE//channelicon/LOGO_Nickelodeon2.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/303/303.mpd",
                keyId: "9130a6448a74430794d355b48b56a64c",
                key: "c2f4d3288cdb43cf81e519ceb414dd6f"
            
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE//channelicon/Nickjr_2024.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/304/304.mpd",
                keyId: "641c3f0e676d49d18c2082e093380e69",
                key: "e06f3a2e327643249c3831ab199c4015"
            
            },
            {
                name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE///channelicon//3BBAsian_new.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/101/101.mpd",
                keyId: "dac6cbd9d17a451bb76386f52469e0e9",
                key: "2e2ac52cadf843459915eaa1a9b95e48"
            
            },
            {
            	name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE///channelicon//Mono29Plus_new.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/109/109.mpd",
                keyId: "072eeb02f6744f838fcc8f0ef36b312e",
                key: "b797c12f2dd64728aae23fd3c8ef275c"    
            },
            {
            	name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE//channelicon/R_0148.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/103/103.mpd",
                keyId: "9c5735afb4fd402580360aed8364469c",
                key: "128d55d9ac2b47ad85f86b5d08320179"    
            },
            {
            	name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon//0149.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/104/104.mpd",
                keyId: "0db89bae851440a5994f5893ad480494",
                key: "d88ef77eaedf4451a65be2e0bf6eabde"    
            },
            {
            	name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon//0151.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/105/105.mpd",
                keyId: "7c04b8e7aa524afea879b2ed1aef8242",
                key: "91e72b75fcb94c3bb36cceb741afd621"    
            },
            {
            	name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE/channelicon/0150.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/106/106.mpd",
                keyId: "07b138f30ad3441ca5a2f476e550af25",
                key: "826ee4deef4b45cfafd5f79a591b15c6"    
            },
            {
            	name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE//channelicon/0147.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/107/107.mpd",
                keyId: "f48caba466394e93b50780f21798787a",
                key: "9a074a10db4342e7937076b3e52f6029"    
            },
            {
            	name: "",
                logo: "https://ais-s.ais-vidnt.com/ais/play/origin/LIVE///channelicon//3BBsports1_new.png",
                file: "https://cri-streamer3.cdn.3bbtv.com:8443/3bb/live/401/401.mpd",
                keyId: "678bbba596584ad895d2923fb0255e82",
                key: "c55471086c824112b217743a31abdf8f"    
            }
            
  ];

        function loadPlayer(channel) {
            jwplayer("player").setup({
                file: channel.file,
                type: "dash",
                drm: {
                    clearkey: {
                        keyId: channel.keyId,
                        key: channel.key
                    }
                },
                width: "100%",
                aspectratio: "16:9",
                autostart: true,
                mute: false
            });
        }

        const channelList = document.getElementById("channel-list");
        channels.forEach(channel => {
            const div = document.createElement("div");
            div.className = "channel";
            div.innerHTML = `<img src="${channel.logo}" alt="${channel.name}"><br>${channel.name}`;
            div.onclick = () => loadPlayer(channel);
            channelList.appendChild(div);
        });

        // เริ่มเล่นเมื่อผู้ใช้กดปุ่ม
        document.getElementById("startPlayback").onclick = () => {
            loadPlayer(channels[0]); // โหลดช่องแรก
            document.getElementById("startPlayback").style.display = "none"; // ซ่อนปุ่ม
        };
    </script>
</body>
</html>