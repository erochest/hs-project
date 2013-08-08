
PROJECT = Pathname.new(Dir.pwd).basename

guard :shell do
  watch(/.*\.cabal$/) do
    system %{cabal-dev configure --enable-tests}
    puts "Configured"
  end
end

guard :shell do
  watch(/.*.l?hs$/) do
    system %{cabal-dev build}
    system %{./dist/build/#{PROJECT}-specs/#{PROJECT}-specs}
  end
end

