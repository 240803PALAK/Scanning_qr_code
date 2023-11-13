# Scanning_qr_code

    from pyzbar.pyzbar import decode
    from Pil import Image
    import cv2
    import webbrowser
    
    video.cv2.VideoCapture(0)
    while True:
        open,frame=video.read()
        d=decode(frame)
        try:
            for obj in d:
                data = obj.data.decode('utf-8')
                print("QR code data:", data)
                if data.startswith('http'):
                    webbrowser.open(qr_data)
                else:
                    print("Scanned data is not a URL.")
        except:
            print(error)
        key=cv2.waitKey(1)
        if key==ord('q'):
            break
    video.release()
    cv2.destroyAllWindows()
