# aws-cfn-practice

1. スタック作成コマンド
```
aws cloudformation create-stack --template-body file://filepath --stack-name stack-name --parameters file://filepath
(例)
aws cloudformation create-stack --template-body file://~/dev/aws/aws-cfn-practice/practice/vpc3.yml  --stack-name aws-cli-test --parameters file://~/dev/aws/aws-cfn-practice/practice/vpc3-params.yml
```

2. 変更セット作成コマンド
```
aws cloudformation create-change-set --change-set-name 〇〇 --template-body file:///home/ec2-user/cf.yaml --stack-name 〇〇 --parameters file://home/ec2-user/param.json
(例)
aws cloudformation create-change-set --change-set-name aws-cli-test-change-set --template-body file://~/dev/aws/aws-cfn-practice/practice/vpc3.yml --stack-name aws-cli-test --parameters file://~/dev/aws/aws-cfn-practice/practice/vpc3-params.yml
```

3. 変更セットの実行コマンド
```
aws cloudformation execute-change-set --change-set-name change-set-name --stack-name stack-name
(例)
aws cloudformation execute-change-set --change-set-name aws-cli-test-change-set --stack-name aws-cli-test
```

4. スタックの削除コマンド
```
aws cloudformation delete-stack --stack-name stack-name
(例)
aws cloudformation delete-stack --stack-name aws-cli-test
```

5. ParameterStore登録コマンド
```
aws ssm put-parameter --name MasterUsername --type String --value "MasterUsername"
```
