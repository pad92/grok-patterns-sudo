require "yaml"

desc "test"
task :test do
  sh "ruby test/test.rb"
end

desc "show all the variables generated by the filters"
task :show_variable do
  found = {}
  test_dir = Dir.new(File.dirname(__FILE__) + "/test")

  test_dir.each do |e|
    next unless e =~ /\.(yml|yaml)$/
    yaml = YAML.load_file(test_dir.to_path + "/" + e)
    if yaml["results"]
      yaml["results"].keys.each do |k|
        found[k] = true
      end
    end
  end

  found.keys.sort.each do |k|
    puts k
  end
end
