require 'aws-sdk-s3'
require 'aws-sdk-ec2'
require 'colorize'
#
# DEF LIST
#
###########################################################################
# list buckets
def list_buckets
  s3 = Aws::S3::Client.new(
    region: 'us-east-1'
  )
  resp = s3.list_buckets({})
  # get the total number of buckets
  num_buckets = resp.buckets.length
  # loop through and puts name
  num_buckets.times do |i|
    puts resp.buckets[i].name.colorize(:light_magenta).colorize(:background => :black)
  end
end
#
# TASK LIST
#
###########################################################################
desc 'List all buckets'
task :list_buckets do
  list_buckets
end
