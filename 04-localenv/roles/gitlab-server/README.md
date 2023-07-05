
# POST-steps
执行完成上述步骤，需要修改root密码

```bash
[root@VM-4-15-centos info]# docker exec -it gitlab bash
root@823985e03d9e:/# gitlab-rails console -e production
--------------------------------------------------------------------------------
 Ruby:         ruby 2.7.5p203 (2021-11-24 revision f69aeb8314) [x86_64-linux]
 GitLab:       15.3.3-ee (1615d086ad8) EE
 GitLab Shell: 14.10.0
 PostgreSQL:   13.6
------------------------------------------------------------[ booted in 40.99s ]
Loading production environment (Rails 6.1.6.1)
irb(main):001:0> user = User.where(username: 'root').first
=> #<User id:1 @root>
irb(main):002:0> user.password = 'aaaaaaaaaaa'
=> "aaaaaaaaaaaaaa"
irb(main):003:0> user.save!
=> true
irb(main):004:0> exit
root@823985e03d9e:/# exit
[root@VM-4-15-centos info]#
```

