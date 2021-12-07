root
Tjdnfxmrquftl1
Dnftksrhkddurtl1
Dnftksrhkddurtlskarntlswjd1ehd

# 평가지

## Preliminary tests
Defense can only happen if the student being evaluated or group is present.
This way everybody learns by sharing knowledge with each other.
If no work has been submitted (or wrong files, wrong directory, or
wrong filenames), the grade is 0, and the evaluation process ends.
For this project, you have to clone their Git repository on their station.

예비시험
방어는 평가받는 학생이나 그룹이 있는 경우에만 가능합니다.
이러한 방식으로 모든 사람은 서로 지식을 공유하면서 배웁니다.
작업이 제출되지 않은 경우(또는 잘못된 파일, 잘못된 디렉터리 또는
잘못된 파일 이름), 등급이 0이고 평가 프로세스가 종료됩니다.
이 프로젝트의 경우 해당 스테이션에 있는 Git 저장소를 복제해야 합니다.


## General instructions
During the defense, as soon as you need help to verify a point, the student
evaluated must help you.
Ensure that the "signature.txt" file is present at the root of the cloned
repository.
Check that the signature contained in "signature.txt" is identical
to that of the ".vdi" file of the virtual machine to be evaluated. A simple
"diff" should allow you to compare the two signatures. If necessary, ask the
student being evaluated where their ".vdi" file is located.
As a precaution, you can duplica-te the initial virtual machine in order
to keep a copy.
Start the virtual machine to be evaluated.
If something doesn't work as expected or the two signatures differ,
the evaluation stops here.



일반지시
변론을 하는 동안, 여러분이 요점을 확인하는 데 도움이 필요한 즉시, 평가된 학생은 여러분을 도와야 합니다.
복제된 저장소의 루트에 "signature.txt" 파일이 있는지 확인합니다.
signature.txt에 포함된 서명이 동일한지 확인합니다.
평가 대상 가상 시스템의 ".vhd" 파일의 파일로 이동합니다. 간단한 "diff"를 사용하면 두 서명을 비교할 수 있습니다. 필요한 경우 평가 대상 학생에게 ".vdi" 파일이 어디에 있는지 묻습니다.
예방 조치로 복사본을 보관하기 위해 초기 가상 시스템을 복제할 수 있습니다.
평가할 가상 시스템을 시작합니다.
예상대로 작동하지 않거나 두 서명이 다르면
평가는 여기서 중단됩니다.

ssh -p 4242 yunselee@127.0.0.1

## Mandatory part



Project overview
The student being evaluated should explain to you simply:
How a virtual machine works.
Their choice of operating system.
The basic differences between CentOS and Debian.
The purpose of virtual machines.
If the evaluated student chose CentOS: what SELinux and DNF are.
If the evaluated student chose Debian: the difference between aptitude and apt, and what APPArmor is.
During the defense, a script must display information all every 10 minutes. Its operation will be checked in detail later.
If the explanations are not clear, the evaluation stops here.


## Simple setup

Remember: Whenever you need help checking something, the student being evaluated should be able to help you.
Ensure that the machine does not have a graphical environment at launch.
A password will be requested before attempting to connect to this machine.
Finally, connect with a user with the help of the student being evaluated.
This user must not be root.
Pay attention to the password chosen, it must follow the rules imposed in the subject.
Check that the UFW service is started with the help of the evaluator.

프로젝트 개요
평가 대상 학생은 다음과 같이 간단히 설명해야 합니다.
- 가상 시스템의 작동 방식입니다. 물리장치를 모두 가상으로 구현하여 컴퓨터 안의 컴퓨터를 사용할수있도록 세팅
- 운영체제에 대한 그들의 선택. debian
- CentOS와 Debian의 기본적인 차이점.

CentOS 7은 POWER9을 추가 지원하는 반면 Debian 및 CentOS 8은 그렇지 않습니다. CentOS 7은 x86_64/AMD64 아키텍처에 중점을 두고 있으며, 다른 아치들은 AltArch SIG(Alternate Architecture Special Interest Group)를 통해 Cent와 함께 릴리즈됩니다.OS 8은 x86_64/AMD64, AArch64 및 ppc64le을 동일하게 지원합니다.

Debian이 MIPSel, MIPS64el 및 s390x를 지원하는 반면 CentOS는 그렇지 않습니다. 머치 라이크 센트OS 8, Debian은 한 아치를 다른 아치에 비해 선호하지 않습니다. 지원되는 모든 아키텍처는 동일하게 지원됩니다.

CentOS uses the RPM package format and YUM/DNF as the package manager.
Debian uses the DEB package format and dpkg/APT as the package manager.


- 가상 시스템의 용도입니다.
- 평가된 학생이 Cent를 선택한 경우OS: SELinux와 DNF가 무엇인지.
- 만약 평가된 학생이 데비안을 선택했다면: aptitude apt 차이, 그리고 APP Armor가 무엇인지.
apt는 다른 하이레벨 패키지 매니저에 의해 사용될 수 있음
aptitude는 사용하지 않는 패키지를 자동적으로 제거해준다. 반면 apt는 추가적 옵션이 필요하다. (ex. 'autoremove', '-auto-remove')
apt에서 각각 upgrade와 dist-upgrade로 쓰이던 커맨드는 safe-upgrade와 full-upgrade로 바뀌었다.(보다 명확히 하기 위해?)
aptitude는 apt-get 외에 apt-chche, apt-mark와 같은 툴도 같이 사용한다.
aptitude는 검색에서 조금 다른 쿼리 신택스를 사용한다 (apt-cache와 비교했을 때)
aptitude는 why와 why-not 커맨드를 통해 특정 패키지를 설치할 때 어떤 것이 요구되고, 어떤 것과 충돌하는지 확인할 수 있다.
aptitude는 설치, 제거, 업데이트 과정에서 충돌이 있는 경우 다른 대안을 제시해줌. apt는 그냥 안 된다고만 함.

앱아머는 정책 파일을 통해 어떤 어플리케이션이 어떤 파일/경로에 접근 가능한지 허용해준다.
enforce모드와 complain모드 두 가지 존재
enforce 모드 : 허가되지 않은 파일에 접근하는 것을 거부하는 모드
complain 모드 : 실질적으로 보안을 제공하는 것은 아님. 대신 어플리케이션이 해야 할 행동이 아닌 다른 행동을 하는 경우에 앱아머는 로그를 남겨준다(중지하지는 않음).
"sudo aa-status"통해 현재 상태 확인 가능(enforced, complain, unconfined)
"ps auxZ | grep -v '^unconfined'" 통해 현재 앱아머에 의해 제한된 실행 파일 확인 가능


방어 중에는 스크립트가 10분마다 모든 정보를 표시해야 합니다. 그 작동은 나중에 자세히 확인될 것이다.
설명이 명확하지 않은 경우 평가는 여기서 중단됩니다.


간단한 설정
명심할 사항: 여러분이 무언가를 점검하는 데 도움이 필요할 때마다, 평가를 받는 학생이 여러분을 도울 수 있을 거예요.
시스템을 시작할 때 그래픽 환경이 없는지 확인합니다.
이 시스템에 연결하기 전에 암호를 요청합니다.
마지막으로, 평가 대상 학생의 도움을 받아 사용자와 연결합니다.
이 사용자는 루트가 아니어야 합니다.
선택한 암호는 제목에 지정된 규칙을 따라야 합니다.
평가자의 도움을 받아 UFW 서비스가 시작되었는지 확인합니다.

ssh -p 4242 yunselee@127.0.0.1
**sudo systemctl status ufw

Check that the SSH service is started with the help of the evaluator.
SSH 서비스가 평가자의 도움을 받아 시작되었는지 확인합니다.

**sudo systemctl status ssh


Check that the chosen operating system is Debian or CentOS with the help of the evaluator.
If something does not work as expected or is not clearly explained, the evaluation stops here.
선택한 운영 체제가 Debian 또는 Cent인지 점검하십시오.평가자의 도움을 받는 OS.
예상대로 작동하지 않거나 명확하게 설명되지 않은 경우 평가는 여기서 중단됩니다.


## User

Remember: Whenever you need help checking something, the student being evaluated should be able to help you.
The subject requests that a user with the login of the student being evaluated is present on the virtual machine. Check that it has been added and that it belongs to the "sudo" and "user42" groups.

사용자

명심할 사항: 여러분이 무언가를 점검하는 데 도움이 필요할 때마다, 평가를 받는 학생이 여러분을 도울 수 있을 거예요.
평가 중인 학생의 로그인이 있는 사용자가 가상 시스템에 있어야 하는 주체 요청입니다. 추가되었고 "sudo" 및 "user42" 그룹에 속해 있는지 확인합니다.

**groups

Make sure the rules imposed in the subject concerning the password policy have been put in place by following the following steps.

다음 단계에 따라 암호 정책과 관련하여 주제에 부과된 규칙이 적용되었는지 확인하십시오.


First, create a new user. Assign it a password of your choice, respecting the subject rules. The student being evaluated must now explain to you how they were able to set up the rules requested in the subject on their virtual machine.
Normally there should be one or two modified files. If there is any problem, the evaluation stops here.

Now that you have a new user, ask the student being evaluated to create a group named "evaluating" in front of you and assign it to this user. Finally, check that this user belongs to the "evaluating" group.

Finally, ask the student being evaluated to explain the advantages of this password policy, as well as the advantages and disadvantages of its implementation. Of course, answering that it is because the subject asks for it does not count.

If something does not work as expected or is not clearly explained, the evaluation stops here.

먼저 새 사용자를 생성합니다. 제목 규칙에 따라 선택한 암호를 지정합니다. 평가 중인 학생은 이제 가상 시스템의 제목에서 요청한 규칙을 어떻게 설정할 수 있었는지 설명해야 합니다.
일반적으로 한두 개의 수정된 파일이 있어야 합니다. 문제가 있는 경우 평가가 여기서 중지됩니다.
이제 새로운 사용자가 생겼으니, 평가 대상 학생에게 여러분 앞에 "evaluating"이라는 이름의 그룹을 만들어 이 사용자에게 할당하도록 요청하십시오. 마지막으로 이 사용자가 "evaluating" 그룹에 속해 있는지 확인합니다.
마지막으로 평가 대상 학생에게 이 암호 정책의 장점과 단점을 설명하도록 요청합니다. 물론, 주제가 그것을 요구하기 때문이라고 대답하는 것은 중요하지 않다.

예상대로 작동하지 않거나 명확하게 설명되지 않은 경우 평가는 여기서 중단됩니다.
password

"sudo vi /etc/login.defs"친 후, "PASS_MAX_DAYS 30", "PASS_MIN_DAYS 2", "PASS_WARN_AGE 7", "PASS_MIN_LEN 10"
sudo apt install libpam-pwquality
sudo vi /etc/pam.d/common-password
"passwd -e 사용자명" 통해 root계정과 현존하는 사용자 계정의 암호 변경을 강제한다. 다음 번 로그인시에 암호를 변경하라고 뜨게 된다.
retry=3 : 암호 입력 3회까지
minlen=10 : 암호 최소 길이는 10
difok=7 : 기존 패스워드와 달라야하는 문자 수는 7
ucredit=-1 : 대문자 한 개 이상
lcredit=-1 : 소문자 한 개 이상
dcredit=-1 : 숫자 한 개 이상
reject_username : username이 그대로 또는 뒤집혀서 새 패스워드에 들어있는지 검사하고, 들어있으면 거부
enforce_for_root : root 사용자가 패스워드를 바꾸려고 하는 경우에도 위의 조건들 적용



useradd
passwd
groupadd evaluating
usermod -aG evaluating 사용자명
groupdel ~
groups
userdel ~


## Hostname and partitions

Remember: Whenever you need help checking something, the student being evaluated should be able to help you.

Check that the hostname of the machine is correctly formatted as follows: login42 (login of the student being evaluated).
Modify this hostname by replacing the login with yours, then restart the machine.
If on restart, the hostname has not been updated, the evaluation stops here.
You can now restore the machine to the original hostname.
Ask the student being evaluated how to view the partitions for this virtual machine.
Compare the output with the example given in the subject. Please note: if the student evaluated makes the bonuses, it will be necessary to refer to the bonus example.

This part is an opportunity to discuss the scores! The student being evaluated should give you a brief explanation of how LVM works and what it is all about.
If something does not work as expected or is not clearly explained, the evaluation stops here.

호스트 이름 및 파티션
명심할 사항: 여러분이 무언가를 점검하는 데 도움이 필요할 때마다, 평가를 받는 학생이 여러분을 도울 수 있을 거예요.

기계의 호스트 이름이 로그인42(평가 중인 학생의 로그인)와 같이 올바르게 포맷되어 있는지 확인합니다.
로그인을 사용자 계정으로 교체하여 이 호스트 이름을 수정한 다음 시스템을 다시 시작합니다.
재시작 시 호스트 이름이 업데이트되지 않은 경우 평가는 여기서 중지됩니다.
이제 시스템을 원래 호스트 이름으로 복원할 수 있습니다.
평가 중인 학생에게 이 가상 시스템의 파티션을 보는 방법을 묻습니다.
제목에 주어진 예와 출력을 비교합니다. 참고: 평가된 학생이 보너스를 지급하는 경우 보너스 예를 참조해야 합니다.

이 파트는 점수에 대해 논의할 기회입니다! 평가 대상 학생은 LVM의 작동 방식과 작동 원리에 대해 간략하게 설명해야 합니다.
예상대로 작동하지 않거나 명확하게 설명되지 않은 경우 평가는 여기서 중단됩니다.


sudo hostnamectl set-hostname 바꾸려는호스트명
hostnamectl

## SUDO
Remember: Whenever you need help checking something, the student being evaluated should be able to help you.

Check that the "sudo" program is properly installed on the virtual machine.
The student being evaluated should now show assigning your new user to the "sudo" group.
The subject imposes strict rules for sudo. The student being evaluated must first explain the value and operation of sudo using examples of their choice.
In a second step, it must show you the implementation of the rules imposed by the subject.
Verify that the "/var/log/sudo/" folder exists and has at least one file. Check the contents of the files in this folder, You should see a history of the commands used with sudo.
Finally, try to run a command via sudo. See if the file (s) in the "/var/log/sudo/" folder have been updated.
If something does not work as expected or is not clearly explained, the evaluation stops here.

SUDO
명심할 사항: 여러분이 무언가를 점검하는 데 도움이 필요할 때마다, 평가를 받는 학생이 여러분을 도울 수 있을 거예요.

가상 시스템에 "sudo" 프로그램이 올바르게 설치되어 있는지 확인합니다.
평가 중인 학생은 이제 새 사용자를 "sudo" 않은그룹에 할당하는 방법을 보여야 합니다.
그 과목은 스도에 대해 엄격한 규칙을 부과한다. 평가 대상 학생은 먼저 선택한 예를 사용하여 수도의 가치와 작동 방식을 설명해야 합니다.
두 번째 단계에서는 주체에 의해 부과된 규칙의 이행을 보여줘야 합니다.
/var/log/sudo/" 폴더가 있고 파일이 하나 이상 있는지 확인합니다. 이 폴더의 파일 내용을 확인합니다. sudo에 사용된 명령의 기록이 표시됩니다.
마지막으로 sudo를 통해 명령을 실행해 봅니다. /var/log/sudo/" 폴더의 파일이 업데이트되었는지 확인합니다.
예상대로 작동하지 않거나 명확하게 설명되지  경우 평가는 여기서 중단됩니다.


sudo visudo

## UFW
Remember: Whenever you need help checking something, the student being evaluated should be able to help you.

Check that the "UFW" program is properly installed on the virtual machine.
Check that it is working properly.
The student being evaluated should explain to you basically what UFW is and the value of using it.
List the active rules in UFW. A rule must exist for port 4242.
Add a new rule to open port 8080. Check that this one has been added by listing the active rules.
Finally, delete this new rule with the help of the student being evaluated.
If something does not work as expected or is not clearly explained, the evaluation stops here.

UFW
명심할 사항: 여러분이 무언가를 점검하는 데 도움이 필요할 때마다, 평가를 받는 학생이 여러분을 도울 수 있을 거예요.

가상 시스템에 "UFW" 프로그램이 올바르게 설치되어 있는지 확인합니다.
올바르게 작동하는지 확인합니다.
평가 대상 학생은 기본적으로 UFW가 무엇이며 UFW가 얼마나 유용한지 설명해야 합니다.
UFW에 활성 규칙을 나열합니다. 포트 4242에 대한 규칙이 있어야 합니다.
포트 8080을 여는 데 새 규칙을 추가합니다. 활성 규칙을 나열하여 이 규칙이 추가되었는지 확인하십시오.
마지막으로, 평가 중인 학생의 도움을 받아 이 새 규칙을 삭제하십시오.
예상대로 작동하지 않거나 명확하게 설명되지 않은 경우 평가는 여기서 중단됩니다.

"sudo ufw status verbose"로 ufw 상태 확인 (디폴트는 inactive)
"sudo ufw allow 4242"로 ssh연결 허용(4242라는 커스텀 포트 사용하는 경우)
정책 삭제 원하는 경우 "sudo ufw status numbered"로 지우고 싶은 규칙 확인후 "sudo ufw delete 규칙번호"입력


## SSH

Remember: Whenever you need help checking something, the student being evaluated should be able to help you.

Check that the SSH service is properly installed on the virtual machine.
Check that it is working properly.
The student being evaluated must be able to explain to you basically what SSH is and the value of using it.
Verify that the SSH service only uses port 4242.
The student being evaluated should help you use SSH in order to log in with the newly created user.
To do this, you can use a key or a simple password. It will depend on the student being evaluated.
Of course, you have to make sure that you cannot use SSH with the "root" user as stated in the  subject.
If something does not work as expected or is not clearly explained, the evaluation stops here.
SSH

명심할 사항: 여러분이 무언가를 점검하는 데 도움이 필요할 때마다, 평가를 받는 학생이 여러분을 도울 수 있을 거예요.

SSH 서비스가 가상 시스템에 올바르게 설치되어 있는지 확인합니다.
올바르게 작동하는지 확인합니다.
평가 대상 학생은 기본적으로 SSH가 무엇이며 SSH를 사용하는 가치를 설명할 수 있어야 합니다.
SSH 서비스가 포트 4242만 사용하는지 확인합니다.
평가 중인 학생은 새로 생성된 사용자로 로그인하기 위해 SSH를 사용할 수 있도록 도와야 합니다.
이를 위해 키 또는 단순 암호를 사용할 수 있습니다. 그것은 평가받는 학생에 달려있다.
물론 제목에 명시된 대로 SSH를 "루트" 사용자와 함께 사용할 수 없도록 해야 합니다.
예상대로 작동하지 않거나 명확하게 설명되지 않은 경우 평가는 여기서 중단됩니다.

sudo systemctl status ssh
sudo ufw status verbose

Secure Shell Protocol, 즉 네트워크 프로토콜 중 하나로 컴퓨터와 컴퓨터가 인터넷과 같은 Public Network를 통해 서로 통신을 할 때 보안적으로 안전하게 통신을 하기 위해 사용하는 프로토콜입니다. 
기존의 rsh, rlogin, 텔넷 등을 대체하기 위해 설계되었으며, 강력한 인증 방법 및 안전하지 못한 네트워크에서 안전하게 통신을 할 수 있는 기능을 제공한다

# Script monitoring

Remember: Whenever you need help checking something, the student being evaluated
should be able to help you.

The student being evaluated should explain to you simply: How their script works by showing you the code.
What "cron" is.
How the student being evaluated set up their script so that it runs every 10 minutes from when the server starts.
Once the correct functioning of the script has been verified, the student being evaluated should ensure that this script runs every minute. You can run whatever you want to make sure the script runs with dynamic values correctly. Finally, the student being evaluated should make the script stop running when the server has started up, but without modifying the script itself. To check this point, you will have to restart the server one last time. At startup, it will be necessary to check that the script still exists in the same place, that its rights have remained unchanged, and that it has not been modified.
If something does not work as expected or is not clearly explained, the evaluation stops here.

스크립트 모니터링
명심할 사항: 점검하는 데 도움이 필요할 때마다 평가받는 학생
널 도울 수 있을 거야

평가 대상 학생은 다음과 같이 간단히 설명해야 합니다. 코드를 표시하여 스크립트의 작동 방식을 설명합니다.
'크론'이란 무엇인가?
평가 대상 학생이 서버가 시작될 때부터 10분마다 실행되도록 스크립트를 설정하는 방법입니다.
스크립트가 올바르게 작동하는지 확인한 후 평가 대상 학생은 이 스크립트를 매 분마다 실행해야 합니다. 스크립트가 동적 값으로 올바르게 실행되도록 원하는 대로 실행할 수 있습니다. 마지막으로 평가 중인 학생은 서버가 시작될 때 스크립트 자체를 수정하지 않고 스크립트 실행을 중지해야 합니다. 이 점을 확인하려면 서버를 마지막으로 다시 시작해야 합니다. 시작할 때 스크립트가 동일한 위치에 있는지, 해당 권한이 변경되지 않았는지, 수정되지 않았는지 확인해야 합니다.
예상대로 작동하지 않거나 명확하게 설명되지 않은 경우 평가는 여기서 중단됩니다.
$ crontab -e
$ crontab -l
$ crontab -r
*　　　　　　*　　　　　　*　　　　　　*　　　　　　*
분(0-59)　　시간(0-23)　　일(1-31)　　월(1-12)　　　요일(0-7)
각 별 위치에 따라 주기를 다르게 설정 할 수 있습니다. 순서대로 분-시간-일-월-요일 순입니다. 그리고 괄호 안의 숫자 범위 내로 별 대신 입력 할 수 있습니다.
매분
* * * * *

shasum
c9b16e9aba694b3fe3de003d4d833789883b053c
signature.txt



------------------------------



ssh -p 4242 yunselee@127.0.0.1

## Mandatory part


- 가상 시스템의 작동 방식입니다. 물리장치를 모두 가상으로 구현하여 컴퓨터 안의 컴퓨터를 사용할수있도록 세팅
- 운영체제에 대한 그들의 선택. debian
- CentOS와 Debian의 기본적인 차이점.

CentOS 7은 POWER9을 추가 지원하는 반면 Debian 및 CentOS 8은 그렇지 않습니다. CentOS 7은 x86_64/AMD64 아키텍처에 중점을 두고 있으며, 다른 아치들은 AltArch SIG(Alternate Architecture Special Interest Group)를 통해 Cent와 함께 릴리즈됩니다.OS 8은 x86_64/AMD64, AArch64 및 ppc64le을 동일하게 지원합니다.

Debian이 MIPSel, MIPS64el 및 s390x를 지원하는 반면 CentOS는 그렇지 않습니다. 머치 라이크 센트OS 8, Debian은 한 아치를 다른 아치에 비해 선호하지 않습니다. 지원되는 모든 아키텍처는 동일하게 지원됩니다.

CentOS uses the RPM package format and YUM/DNF as the package manager.
Debian uses the DEB package format and dpkg/APT as the package manager.


- 가상 시스템의 용도입니다.
- 평가된 학생이 Cent를 선택한 경우OS: SELinux와 DNF가 무엇인지.
- 만약 평가된 학생이 데비안을 선택했다면: aptitude apt 차이, 그리고 APP Armor가 무엇인지.
apt는 다른 하이레벨 패키지 매니저에 의해 사용될 수 있음
aptitude는 사용하지 않는 패키지를 자동적으로 제거해준다. 반면 apt는 추가적 옵션이 필요하다. (ex. 'autoremove', '-auto-remove')
apt에서 각각 upgrade와 dist-upgrade로 쓰이던 커맨드는 safe-upgrade와 full-upgrade로 바뀌었다.(보다 명확히 하기 위해?)
aptitude는 apt-get 외에 apt-chche, apt-mark와 같은 툴도 같이 사용한다.
aptitude는 검색에서 조금 다른 쿼리 신택스를 사용한다 (apt-cache와 비교했을 때)
aptitude는 why와 why-not 커맨드를 통해 특정 패키지를 설치할 때 어떤 것이 요구되고, 어떤 것과 충돌하는지 확인할 수 있다.
aptitude는 설치, 제거, 업데이트 과정에서 충돌이 있는 경우 다른 대안을 제시해줌. apt는 그냥 안 된다고만 함.

앱아머는 정책 파일을 통해 어떤 어플리케이션이 어떤 파일/경로에 접근 가능한지 허용해준다. 리눅스 커널 보안 모듈이
enforce모드와 complain모드 두 가지 존재
enforce 모드 : 허가되지 않은 파일에 접근하는 것을 거부하는 모드
complain 모드 : 실질적으로 보안을 제공하는 것은 아님. 대신 어플리케이션이 해야 할 행동이 아닌 다른 행동을 하는 경우에 앱아머는 로그를 남겨준다(중지하지는 않음).
"sudo aa-status"통해 현재 상태 확인 가능(enforced, complain, unconfined)
"ps auxZ | grep -v '^unconfined'" 통해 현재 앱아머에 의해 제한된 실행 파일 확인 가능


방어 중에는 스크립트가 10분마다 모든 정보를 표시해야 합니다. 그 작동은 나중에 자세히 확인될 것이다.


## Simple setup



ssh -p 4242 yunselee@127.0.0.1
**sudo systemctl status ufw
**sudo systemctl status ssh

## User

**groups

sudo vi /etc/login.defs
"PASS_MAX_DAYS 30", "PASS_MIN_DAYS 2", "PASS_WARN_AGE 7", "PASS_MIN_LEN 10"

sudo apt install libpam-pwquality
sudo vi /etc/pam.d/common-password
"passwd -e 사용자명" 통해 root계정과 현존하는 사용자 계정의 암호 변경을 강제한다. 다음 번 로그인시에 암호를 변경하라고 뜨게 된다.
retry=3 : 암호 입력 3회까지
minlen=10 : 암호 최소 길이는 10
difok=7 : 기존 패스워드와 달라야하는 문자 수는 7
ucredit=-1 : 대문자 한 개 이상
lcredit=-1 : 소문자 한 개 이상
dcredit=-1 : 숫자 한 개 이상
reject_username : username이 그대로 또는 뒤집혀서 새 패스워드에 들어있는지 검사하고, 들어있으면 거부
enforce_for_root : root 사용자가 패스워드를 바꾸려고 하는 경우에도 위의 조건들 적용

useradd
passwd
groupadd evaluating
usermod -aG evaluating 사용자명
groupdel ~
groups
userdel ~


## Hostname and partitions

LVM의 작동 방식과 작동 원리에 대해 간략하게 설명
-> PV 생성(pvcreate CMD)
-> VG 생성(vgcreate CMD)
-> LV 생성(lvcreate CMD)


sudo hostnamectl set-hostname 바꾸려는호스트명
hostnamectl

lsblk


Logical Volume Manager


## SUDO



usermod -aG sudo 사용자명

/var/log/sudo/
sudo visudo
sudoreplay -d ./ 00001Z


# UFW


Uncomplicated Firewall


"sudo ufw status verbose"로 ufw 상태 확인 (디폴트는 inactive)
"sudo ufw allow 4242"로 ssh연결 허용(4242라는 커스텀 포트 사용하는 경우)
정책 삭제 원하는 경우 "sudo ufw status numbered"로 지우고 싶은 규칙 확인후 "sudo ufw delete 규칙번호"입력



## ssh


Secure Shell Protocol, 즉 네트워크 프로토콜 중 하나로 컴퓨터와 컴퓨터가 인터넷과 같은 Public Network를 통해 서로 통신을 할 때 보안적으로 안전하게 통신을 하기 위해 사용하는 프로토콜입니다. 
기존의 rsh, rlogin, 텔넷 등을 대체하기 위해 설계되었으며, 강력한 인증 방법 및 안전하지 못한 네트워크에서 안전하게 통신을 할 수 있는 기능을 제공한다

sudo systemctl status ssh
sudo ufw status verbose

sudo vim /etc/ssh/sshd_config


# Script monitoring

$ crontab -e
$ crontab -l
$ crontab -r
*　　　　　　*　　　　　　*　　　　　　*　　　　　　*
분(0-59)　　시간(0-23)　　일(1-31)　　월(1-12)　　　요일(0-7)
각 별 위치에 따라 주기를 다르게 설정 할 수 있습니다. 순서대로 분-시간-일-월-요일 순입니다. 그리고 괄호 안의 숫자 범위 내로 별 대신 입력 할 수 있습니다.


shell code

uname -srvmo
시스템 정보출력
s 커널
r 커널 릴리즈정보
v 버전
m 아키텍처
o 운영체제 이름

nproc --all
프로세싱 유닛의 갯수만을 출력

cat /proc/cpuinfo
free -m 메모리 사용량
-m 메가바이트

df -BM -a
megabyte
df -H -a
G,M...

mpstat

who -b
호스트에 로그인한 사용자의 정보를 출력하는 명령어
-b
time of last system boot

ss grep -i tco
socket 상태 점검
who 

/sbin/ifconfig

/var/log/auth.log

/var/log/sudo




c9b16e9aba694b3fe3de003d4d833789883b053c