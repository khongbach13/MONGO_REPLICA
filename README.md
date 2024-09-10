### B1: Chạy file setup.sh để tạo key xác thực
`bash setup.sh`
### B2: Chạy các container
`docker compose up -d`
### B3: Truy cập vào bash shell container mongo1
`docker exec -it mongo1 bash`
### B4: Trên bash shell mongo1 chạy lệnh sau để truy cập vào mongo shell
`mongosh -u root -p phuonglv`
### B5: Khởi tạo Replica
 `rs.initiate(
  {
    _id: "rs0",
    version: 1,
    members: [
      { _id: 0, host: "mongo1:27017" },
      { _id: 1, host: "mongo2:27017" },
      { _id: 2, host: "mongo3:27017" }
    ]
  }
)`
### B6: Kiểm tra replica
`rs.status()`
