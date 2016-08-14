#!/usr/bin/env ruby

require 'yaml'

task :lint do
  puts '--> Reading file'
  obj = YAML.load_file('quote.yaml')
  puts '--> File successfully read. Checking data types...'
  obj['quotes'].each do |q|
    raise StandardError if q['q_no'].nil?
    raise StandardError if q['quote'].nil?
    raise StandardError if q['author'].nil?
    raise StandardError if q['author_bio'].nil?
    raise StandardError if q['tags'].nil?
    raise StandardError unless q['tags'].is_a?(Array)
  end
  puts "Done! Lint successful"
end

task default: :lint
