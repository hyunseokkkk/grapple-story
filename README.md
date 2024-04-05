# grapple-story

리눅스 리버싱 grapple-story
pwngdb 설치 및 실습
![image](https://github.com/hyunseokkkk/grapple-story/assets/122734649/78fe1d34-2493-4fd9-83ed-01c4a6ca11c3)
disas main
![image](https://github.com/hyunseokkkk/grapple-story/assets/122734649/beaae0f7-a758-426d-8927-98988265fff8)
break point
![image](https://github.com/hyunseokkkk/grapple-story/assets/122734649/c9219933-4411-4a60-8d65-4b7ad290da03)

![image](https://github.com/hyunseokkkk/grapple-story/assets/122734649/cea3340f-f7d7-4028-bf88-7b67ab009369)


dword ptr 는 해당 부분으로 부터 두개의 WORD 만큼(double word) 가져오세요, 참조하세요(ptr) 라는 뜻입니다

![image](https://github.com/hyunseokkkk/grapple-story/assets/122734649/355df29a-1e33-4b33-8f0c-b67777fcc107)
sub dword ptr [rbp - 0x14], eax 명령어에서 rax에 0x6(공격력)이 저장됨을 확인할 수 있다.
![image](https://github.com/hyunseokkkk/grapple-story/assets/122734649/47ba92e1-e7ed-4a9e-8378-982f2b7f83cf)
플레이어가 공격을 하면서(main+255) rax의 값이 0x6으로 변환
[rbp - 0x10] 에서 dword ptr 만큼 (4byte) 이 플레이어의 공격력이 저장
[rbp - 0x14] 에서 dword ptr 만큼(4byte) 이 드래곤의 체력이 저장
![image](https://github.com/hyunseokkkk/grapple-story/assets/122734649/648c66ef-4a9b-4d1e-ab7c-ffcb30515e98)
체력을 초기화하는 코드 부분

 게임이나 프로그램의 변수를 변경하여 새로 저장하는 것을 패치(Patch) 

 1. 캐릭터의 공격력을 증가시켜 게임 클리어
    gdb> x/출력할길이 {메모리주소}
![image](https://github.com/hyunseokkkk/grapple-story/assets/122734649/52a14087-f4ea-4093-9953-13e51495ed39)

    ![image](https://github.com/hyunseokkkk/grapple-story/assets/122734649/ef996408-2bcc-41fc-84f3-1ff49325b129)
결과화면)
![image](https://github.com/hyunseokkkk/grapple-story/assets/122734649/fd0e4ca4-9eff-4efc-aaf7-2eea90538c08)
