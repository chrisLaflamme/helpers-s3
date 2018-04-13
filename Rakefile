require 'aws-sdk-s3'
require 'colorize'

$s3 = Aws::S3::Client.new(
    region: 'eu-west-1'
)

# list buckets
def list_buckets
    bucket_hash = $s3.list_buckets({
    })
    
    bucket_hash.each do 
        puts bucket_hash.buckets(:name)
    end
end

desc "List all buckets"
task :list_buckets do
    list_buckets
end