
[![Galaxy](https://img.shields.io/badge/galaxy-memoryleak.users-blue.svg)](https://galaxy.ansible.com/memoryleak/users) [![Build Status](https://travis-ci.org/memoryleak/ansible-role-users.svg?branch=master)](https://travis-ci.org/memoryleak/ansible-role-users)

memoryleak.users
================

A simple role to manage users.

Requirements
------------

None

Role Variables
--------------

    users_groups: []
    users_users: []
    users_filter_groups: []
    users_filter_users: []
    users_default_group: users



Dependencies
------------

None

Example Playbook
----------------

    - hosts: all
      roles:
        - role: memoryleak.users
          users_filter_groups: ['developers', 'visitors', 'integration']
          users_filter_users: ['john.doe', 'cicd']
          users_groups:
            - name: developers
              state: present
              sudo: true

            - name: visitors
              state: present
              sudo: false

            - name: integration
              state: present
              sudo: nopasswd

            - name: placeholder
              state: present
              sudo: nopasswd

          users_users:
            - name: john.doe
              state: present
              # Password: hello123!
              password: $6$J2OJ2Mvb3jVVkwvR$qz0nnBMwtzz9U2sS20C0iuyj07KhGC/QsLBoTdeo2Jwurj6U22c7UoknG2F1Kklvyd13hkFpPrEVqXXQyOzLj0
              public_key: ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCdMalXirJubfSJu/8zY742O0whspI26g/d5gXWOiGUvCbxUdD8mOUKSvxIW+RKNiQyh9awgag/wTF+7K/RgtTPwVz687a2ZalVGI8/TTeZfldM9SsytCGniX9qyYkha206MV0C2vMbPKsBPFvuMMzZXer/mArl/2a0yDWEUhuHFz2D3ztfLmFVrEUfED8gQfmF4GRFGwlPhKJsMSevSxRaOvdyLfWSnrjVjEnc58W5xEcBXgG03BNZHK5k013tqag06zEC30YBWKqRR2eOf2yfjAkTzoZKM/TRvMaI8IFFH20z8SjuC8q7O1wfp+NEHmB6K7Ml38ByfOGTJiBEwv//
              public_key_comment: John Doe <john.doe@example.com>
              group: developers

            - name: cicd
              state: present
              # Password: hello123!
              password: $6$J2OJ2Mvb3jVVkwvR$qz0nnBMwtzz9U2sS20C0iuyj07KhGC/QsLBoTdeo2Jwurj6U22c7UoknG2F1Kklvyd13hkFpPrEVqXXQyOzLj0
              public_key: ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCdMalXirJubfSJu/8zY742O0whspI26g/d5gXWOiGUvCbxUdD8mOUKSvxIW+RKNiQyh9awgag/wTF+7K/RgtTPwVz687a2ZalVGI8/TTeZfldM9SsytCGniX9qyYkha206MV0C2vMbPKsBPFvuMMzZXer/mArl/2a0yDWEUhuHFz2D3ztfLmFVrEUfED8gQfmF4GRFGwlPhKJsMSevSxRaOvdyLfWSnrjVjEnc58W5xEcBXgG03BNZHK5k013tqag06zEC30YBWKqRR2eOf2yfjAkTzoZKM/TRvMaI8IFFH20z8SjuC8q7O1wfp+NEHmB6K7Ml38ByfOGTJiBEwv//
              groups:
                - visitors
                - integration

            - name: placeholder
              state: present
              # Password: hello123!
              password: $6$J2OJ2Mvb3jVVkwvR$qz0nnBMwtzz9U2sS20C0iuyj07KhGC/QsLBoTdeo2Jwurj6U22c7UoknG2F1Kklvyd13hkFpPrEVqXXQyOzLj0
              public_key: ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCdMalXirJubfSJu/8zY742O0whspI26g/d5gXWOiGUvCbxUdD8mOUKSvxIW+RKNiQyh9awgag/wTF+7K/RgtTPwVz687a2ZalVGI8/TTeZfldM9SsytCGniX9qyYkha206MV0C2vMbPKsBPFvuMMzZXer/mArl/2a0yDWEUhuHFz2D3ztfLmFVrEUfED8gQfmF4GRFGwlPhKJsMSevSxRaOvdyLfWSnrjVjEnc58W5xEcBXgG03BNZHK5k013tqag06zEC30YBWKqRR2eOf2yfjAkTzoZKM/TRvMaI8IFFH20z8SjuC8q7O1wfp+NEHmB6K7Ml38ByfOGTJiBEwv//
              groups:
                - visitors
                - integration



License
-------

BSD

Author Information
------------------

Haydar Ciftci <haydar.ciftci@gmail.com>
