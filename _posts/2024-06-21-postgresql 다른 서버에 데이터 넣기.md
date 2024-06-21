---
layout : single
title : "postgresql 다른 서버에 데이터 넣기"
categories: postgresql
tag: [postgresql]
toc: true
---

오늘 개발서버 디비에 데이터를 밀어 넣아야 했다. 문제는 dump파일을 서버 컴퓨터에 넣어서 거기서 푸는게 아니라
로컬에 있는 dump파일을 서버 컴퓨터에 원격으로(?) 넣어야 했다. 

방법은 
pg_dump -U postgres -d drone_dims_db | psql -h 10.137.1.164 -U drone_fmc_user -d fmc
명령어로 가능했다.

추가로 덤프 및 리스토어하는 법이다.
덤프 하는 법
해당 경로 이동 후 : pg_dump -Fc -f 20240621_fmc.dump -U postgres -d drone_fmc_db -t tb_fmc_*
리스토어 하는 법
해당 경로 이동 후 :pg_restore -U postgres -d drone_dims_db 20240621_fmc.dump


  
    
