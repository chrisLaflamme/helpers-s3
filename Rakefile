require 'aws-sdk-s3'
require 'colorize'

$s3 = Aws::S3::Client.new(
  region: 'us-east-1'
)
#
# DEF LIST
#
###########################################################################
# list buckets
def list_buckets
  resp = $s3.list_buckets({})
  # get the total number of buckets
  num_buckets = resp.buckets.length
  # loop through and puts name
  num_buckets.times do |i|
    puts resp.buckets[i].name.colorize(:light_magenta).colorize(:background => :black)
  end
end

# put an object
def send_object(bucket, object_path)
  resp = $s3.put_object({
    body: object_path.to_s, 
    bucket: bucket, 
    key: object_path, 
    # server_side_encryption: "AES256", 
    # tagging: "key1=value1&key2=value2", 
  })
  puts resp.to_h
end
#
# TASK LIST
#
###########################################################################
desc 'List all buckets'
task :list_buckets do
  list_buckets
end

desc 'Send Object to Bucket'
task :send_object do
  puts "Enter the bucket name:"
  @bucket_name = STDIN.gets.chomp.to_s
  puts "Enter the full path of the object to send"
  @object_name = STDIN.gets.chomp.to_s
  send_object(@bucket_name, @object_name)
end
