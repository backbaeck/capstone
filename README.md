# capstone
수어 인식 및 음성 출력 장치
실시간 웹캠 영상 인식 코드
import cv2

def main():
    # 웹캠(기본 장치: 0번) 연결
    cap = cv2.VideoCapture(0)

    if not cap.isOpened():
        print("웹캠을 열 수 없습니다.")
        return

    print("웹캠이 연결되었습니다. 'q'를 눌러 종료하세요.")

    while True:
        # 프레임 읽기
        ret, frame = cap.read()
        if not ret:
            print("프레임을 읽을 수 없습니다.")
            break

        # 프레임 출력
        cv2.imshow("Webcam View", frame)

        # 'q' 키를 누르면 종료
        if cv2.waitKey(1) & 0xFF == ord('q'):
            break

    # 자원 정리
    cap.release()
    cv2.destroyAllWindows()

if __name__ == "__main__":
    main()
